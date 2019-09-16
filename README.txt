<?php

/**
 * FUNCAO xajaxResponse() :: construtor do objeto de resposta a requisições xajax
 * recebe como parametro o charset para parametrização da resposta.
 */
$objResponse = new xajaxResponse('utf-8');
########################################################################################

/**
 * FUNCAO addAssign() :: retorna valores para a view substituindo valores já existentes 
 * ou criando novos elementos com valores de retorno
 * addAssign(seletor, atributo, valor de retorno)
 */
$objResponse->addAssign('#selector', 'attibuteName', $returnValue);
########################################################################################

/** 
 * Formata retorno para XML,
 * obs: deve ser chamado sempre.
 */
return $objResponse->getXML();
########################################################################################

/**
 * Parametriza um alerta na tela (view).
 */
$objResponse->addAlert("Cliente cadastro com sucesso");
########################################################################################

/**
 * A função addRedirect() :: retorna com o objResponse um redirecionamento
 * para o destino passado como parametro.
 * @var string Conteúdo do script.
 */
$objResponse->addRedirect('index.php');
########################################################################################

/**
 * METODO registerFunction() :: Registra a função de resposta ajax 
 * para que ela possa ser chamada a partir do arquivo da view.
 * @var string recebe o nome da função a ser executada.
 */
$xajax->registerFunction("insert");
########################################################################################

/**
 * METODO registerFunction() :: Retorna um script js que será executado na view
 * @var string Conteúdo do script.
 */
$xajax->addScript('console.log(variable)');
########################################################################################

/**
 * METODO registerExternalFunction() :: Registra uma função PHP para ser chamado 
 * através do xajax que está localizado em algum outro arquivo.
 * EX: $xajax->registerExternalFunction('loadCentroCusto', './pasta/arquivo.php.inc');
 * @var string Conteúdo do script.
 */
$xajax->registerExternalFunction("myFunction","myFunction.inc.php",XAJAX_POST);
########################################################################################

/**
 * Você pode usar o xajax para efetuar testes de respostas e conteúdo de variaveis direto no seu navegador.
 * É possível enviar os dados como um JSON para view como no exemplo abaixo:
 * @var string Conteúdo do script.
 */
$data = 'teste de valor';
$objResponse->addScript('variavel =' . json_encode($data));
/**
 * Apos retornar o objeto, a variável ficará disponível no seu navegador, podendo ser 
 * acessada no console.
 */
########################################################################################

