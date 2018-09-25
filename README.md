* Problema: Este sistema não permite mais consultar a última atualização feita - apenas a primeira.

# Rastreamento de Pedidos - Correios
Script para Rastreamento de Pedidos dos Correios usando PHP + SOAP.

Esta é uma classe estatica criada com intuito de rastrear objetos dos correios utilizando para isso PHP e a tecnologia SOAP.
Fique a vontade para usar como desejar, em vosso sistema, seja 
ele pessoal ou comercial. 

O único intuito aqui é apresentar de forma simples o 
funcionamento da API fornecida pelos correios e dar uma solução 
para as pessoas que enfrentam problemas ao usar a API XML antiga.

## Como usar (Todos os Scripts abaixo podem ser encontrados no arquivo exemplo-01.php)
Comece adicionando a classe ao seu script PHP (require), defina os parametros usados ($_params) e inicie o objeto (::init).
```php
require_once 'AjustarCaminho/rastrear.class.php';

// parametros (Alterar "user" e "pass" caso tenha contrato com Correios - consultar manual do Correios caso queira saber das outras questões)
$_params = array( 'user' => 'ECT', 'pass' => 'SRO', 'tipo' => 'L', 'resultado' => 'T', 'idioma' => 101 );

// iniciando objeto
Rastrear::init( $_params );
```

Reforçando: Consulte o manual para entender todos os parametros ('L', 'T', etc).

### Realizando um rastreamento
```php
$obj = Rastrear::get( 'PE012345678BR' ); //Alterar ou definir variável que receba o código do Correios
// Obter resultados
``` 

### Visualizando eventos do Objeto
Os dados retornados estão dentro do objeto "$obj" que foi populado acima. Basta obter os resultados - exemplo: 
```# Visualizando dados basicos do objeto
echo "NUMERO: "    . $obj -> numero . "<br>" ;
// .... 
```
Obs: Tomar cuidado com alguns resultados que nem sempre são retornados (citados no script exemplo-01.php)

### Autor
Autor: Wanderlei Santana <sans.pds@gmail.com>
Alterações por: Giiozero
site (Autor): http://sooho.com.br
Data de Criação: 2016.08.22 00:13h
Copyleft 2015
