# Laravel 5.x OmniPay PayUBiz

Laravel package for PayUBiz payment gateway with Omnipay.

## Install

Via Composer

``` bash
$ composer require appoets/omnipay-payubiz
```

## Usage

### Configuration
``` php
$PayU = OmniAuth::create('PayUBiz');
$PayU->setKey(MERCHANT_ID);
$PayU->setSalt(PAYU_SALT);

$PaymentDetails = [
    'name' => $user->name,
    'first_name' => $user->first_name,
    'last_name' => $user->last_name,
    'email' => $user->email,
    'amount' => $product->amount,
    'product' => $product->name,
    'curl' => url('api/payment/cancelled'),
    'furl' => url('api/payment/failed'),
    'surl' => url('api/payment/success')
];

$PayU->purchase($PaymentDetails)->send()->redirect();
```
Check official OmniPay documentation for more

## Credits
- [Sidharth Raveendran][link-author]
- [Arun Yokesh][link-minions]

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

[link-packagist]: https://packagist.org/packages/appoets/omnipay-payubiz
[link-author]: https://github.com/SidharthRaveendran
[link-minions]: https://github.com/yokesharun
