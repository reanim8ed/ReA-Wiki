# PHP

* Library to work with CSV documents: [https://csv.thephpleague.com](https://csv.thephpleague.com/9.0/)
* A library for validating emails against several RFC: [https://github.com/egulias/EmailValidator](https://github.com/egulias/EmailValidator)
* Iteration of big JSON files or streams: [https://github.com/halaxa/json-machine](https://github.com/halaxa/json-machine)

## Optimizations from nginx

[https://www.nginx.com/blog/9-tips-for-improving-wordpress-performance-with-nginx](https://www.nginx.com/blog/9-tips-for-improving-wordpress-performance-with-nginx/)

## Security headers for WP

[https://solidx.dev/improve-wordpress-security-grade](https://solidx.dev/improve-wordpress-security-grade/)

## Setting up together PHPStorm, PHPUnit, Xdebug and Docker

[https://www.orbitale.io/2019/11/16/setting-up-together-phpstorm-phpunit-xdebug-and-docker.html](https://www.orbitale.io/2019/11/16/setting-up-together-phpstorm-phpunit-xdebug-and-docker.html)

## [PHP NTLM authentication + soap client](https://stackoverflow.com/questions/40218466/php-ntlm-authentication-soap-client)

NTLMStream.php

```
<?php
/*
* Original https://thomas.rabaix.net/blog/2008/03/using-soap-php-with-ntlm-authentication
* Modified by http://blogs.msdn.com/b/freddyk/archive/2010/01/19/connecting-to-nav-web-services-from-php.aspx:
*/

class NTLMStream
{
    private $path;
    private $mode;
    private $options;
    private $opened_path;
    private $buffer;
    private $pos;

    public function stream_open($path, $mode, $options, $opened_path) {
        $this->path = $path;
        $this->mode = $mode;
        $this->options = $options;
        $this->opened_path = $opened_path;
        $this->createBuffer($path);
        return true;
    }
    public function stream_close() {
        curl_close($this->ch);
    }
    public function stream_read($count) {
        if(strlen($this->buffer) == 0) {
            return false;
        }
        $read = substr($this->buffer,$this->pos, $count);
        $this->pos += $count;
        return $read;
    }
    public function stream_write($data) {
        if(strlen($this->buffer) == 0) {
            return false;
        }
        return true;
    }
    public function stream_eof() {
        return ($this->pos > strlen($this->buffer));
    }
    public function stream_tell() {
        return $this->pos;
    }
    public function stream_flush() {
        $this->buffer = null;
        $this->pos = null;
    }
    public function stream_stat() {
        $this->createBuffer($this->path);
        $stat = array(
            'size' => strlen($this->buffer),
        );
        return $stat;
    }
    public function url_stat($path, $flags) {
        $this->createBuffer($path);
        $stat = array(
            'size' => strlen($this->buffer),
        );
        return $stat;
    }
    private function createBuffer($path) {
        if($this->buffer) {
            return;
        }
        $this->ch = curl_init($path);
        curl_setopt($this->ch, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($this->ch, CURLOPT_HTTP_VERSION, CURL_HTTP_VERSION_1_1);
        curl_setopt($this->ch, CURLOPT_HTTPAUTH, CURLAUTH_NTLM);
        curl_setopt($this->ch, CURLOPT_SSL_VERIFYPEER, false);
        curl_setopt($this->ch, CURLOPT_USERPWD, USERPWD);
        $this->buffer = curl_exec($this->ch);
        $this->pos = 0;
    }
}

class NTLMSoapClient extends \SoapClient
{
    function __doRequest($request, $location, $action, $version, $one_way = 0) {
        $headers = array(
            'Method: POST',
            'Connection: Keep-Alive',
            'User-Agent: PHP-SOAP-CURL',
            'Content-Type: text/xml; charset=utf-8',
            'SOAPAction: "'.$action.'"',
        );
        $this->__last_request_headers = $headers;
        $ch = curl_init($location);
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
        curl_setopt($ch, CURLOPT_POST, true );
        curl_setopt($ch, CURLOPT_POSTFIELDS, $request);
        curl_setopt($ch, CURLOPT_HTTP_VERSION, CURL_HTTP_VERSION_1_1);
        curl_setopt($ch, CURLOPT_HTTPAUTH, CURLAUTH_NTLM);
        curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
        curl_setopt($ch, CURLOPT_USERPWD, USERPWD);
        $response = curl_exec($ch);
        return $response;
    }
    function __getLastRequestHeaders() {
        return implode("\n", $this->__last_request_headers)."\n";
    }
}
```

test.php

```
<?php
define('USERPWD', 'domain\username:password');
require_once("NTLMStream.php");
stream_wrapper_unregister("https");
stream_wrapper_register("https", "NTLMStream")
$params = [
    'stream_context' => stream_context_create([
           'ssl' => [
            'ciphers'=>'RC4-SHA', 
            'verify_peer'=>false, 
            'verify_peer_name'=>false, 
            'allow_self_signed'=>true,
        ]),
    'cache_wsdl' => WSDL_CACHE_NONE,
    'soap_version' => SOAP_1_1,
    'trace' => 1,
    'connection_timeout' => 180, 
    'features' => SOAP_SINGLE_ELEMENT_ARRAYS
];
$client = new NTLMSoapClient("https://hostname.com/webservice", $params);
$retVal = $client->ReadMultiple(...
...
```

## Tools

### PHP\_CodeSniffer installation in PHPStorm

{% embed url="https://gist.github.com/reanim8ed/3b0d25a7f6d45e465e053953edee0b4b" %}

### NuSOAP

* [NuSOAP ](https://github.com/econea/nusoap)tai package'as, kuris lyginant su integruotu SOAP klientu turi pranašumą tuom, kad jo pagalba nereikia kurti XML tipo užklausų, jis tai atlieka automatiškai. Labai efektyvu dirbant su WSDL tipo web servisais. Nors originalus paketas jau nebeatnaujinamas kelis metus, tačiau pateikta versija yra originalo fork'as, kuris turi support'ą PHP 5.4 - 7.1 versijoms ir periodiškai atnaujinamas.
