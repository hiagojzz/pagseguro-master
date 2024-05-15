<p align="center"><img src="https://stc.pagseguro.uol.com.br/pagseguro/i/logos/logo_pagseguro200x41.png"></p>

Qualquer problema, dúvida ou sugestão sinta-se livre para abrir uma issue.

```php
use PagSeguro; //Utilize a Facade

try {
    $pagseguro = PagSeguro::setReference('2')
    ->setSenderInfo([
       'senderName' => 'Nome Completo', //Deve conter nome e sobrenome
       'senderPhone' => '(32) 1324-1421', //Código de área enviado junto com o telefone
       'senderEmail' => 'email@email.com',
       'senderHash' => 'Hash gerado pelo javascript',
       'senderCNPJ' => '98.966.488/0001-00' //Ou CPF se for Pessoa Física
    ])
    ->setShippingAddress([
       'shippingAddressStreet' => 'Rua/Avenida',
       'shippingAddressNumber' => 'Número',
       'shippingAddressDistrict' => 'Bairro',
       'shippingAddressPostalCode' => '12345-678',
       'shippingAddressCity' => 'Cidade',
       'shippingAddressState' => 'UF'
     ])
     ->setItems([
      [
        'itemId' => 'ID',
        'itemDescription' => 'Nome do Item',
        'itemAmount' => 12.14, //Valor unitário
        'itemQuantity' => '2', // Quantidade de itens
      ],
      [
        'itemId' => 'ID 2',
        'itemDescription' => 'Nome do Item 2',
        'itemAmount' => 12.14,
        'itemQuantity' => '2',
      ]
    ])
    ->send([
      'paymentMethod' => 'boleto'
    ]);
}
catch(\Artistas\PagSeguro\PagSeguroException $e) {
    $e->getCode(); //codigo do erro
    $e->getMessage(); //mensagem do erro
}
```

#### Créditos
Criador: [hiagojazz](https://github.com/hiagojzz)
Project: [fernandobandeira](https://github.com/fernandobandeira)

[Contribuidores](https://github.com/artistas/laravel-pagseguro/graphs/contributors)

PagSeguro Recorrente (Inicial): [vanessasoutoc](https://github.com/vanessasoutoc)

