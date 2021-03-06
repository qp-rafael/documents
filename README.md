Brazanation Documents
=====================

[![Build Status](https://travis-ci.org/brazanation/documents.svg?branch=master)](https://travis-ci.org/brazanation/documents)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/brazanation/documents/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/brazanation/documents/?branch=master)
[![Code Coverage](https://scrutinizer-ci.com/g/brazanation/documents/badges/coverage.png?b=master)](https://scrutinizer-ci.com/g/brazanation/documents/?branch=master)
[![StyleCI](https://styleci.io/repos/66179431/shield)](https://styleci.io/repos/66179431)

A PHP library to provide Brazilian Documents safer, easier and fun!

Installation
------------

Install the library using [composer][1]. Add the following to your `composer.json`:

```json
{
    "require": {
        "brazanation/documents": "0.1.*"
    }
}
```

Now run the `install` command.

```sh
$ composer.phar install
```

or

```sh
$ composer require brazanation/documents 0.1.*
```

#### CPF (cadastro de pessoas físicas)

Registration of individuals or Tax Identification

```php
use Brazanation\Documents\Cpf;
use Brazanation\Documents\Exception\InvalidDocument as  InvalidDocumentException;

try {
    $cpf = new Cpf('06843273173');
    echo $cpf; // prints 06843273173
    echo $cpf->format(); // prints 068.432.731-73
catch (InvalidDocumentException $e){
    echo $e->getMessage();
}
```

#### CNPJ (cadastro nacional da pessoa jurídica)

Company Identification or National Register of Legal Entities
```php
use Brazanation\Documents\Cnpj;
use Brazanation\Documents\Exception\InvalidDocument as  InvalidDocumentException;

try {
    $cnpj = new Cnpj('99999090910270');
    echo $cnpj; // prints 99999090910270
    echo $cnpj->format(); // prints 99.999.090/9102-70
catch (InvalidDocumentException $e){
    echo $e->getMessage();
}
```

#### PIS/PASEP (programa de integração social e programa de formação do patrimônio do servidor público)

Social Integration Program and Training Program of the Heritage of Public Servant

```php
use Brazanation\Documents\PisPasep;
use Brazanation\Documents\Exception\InvalidDocument as  InvalidDocumentException;

try {
    $pispasep = new PisPasep('51.82312.94-92');
    echo $pispasep; // prints 51823129492
    echo $pispasep->format(); // prints 51.82312.94-92
catch (InvalidDocumentException $e){
    echo $e->getMessage();
}
```

### License

MIT, hell yeah!

[1]: http://getcomposer.org/