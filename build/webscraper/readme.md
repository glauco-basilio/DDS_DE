# Crawler da web

## Objetivo

O objetivo é persistir o HTML em armazenamento temporário para análise procesasmento posterior.

## Armazenamento

A convenção para o nome do arquivo armazenamento é [letra]-[oridnal_da_página].html

## Seletores

O ponto de entrada é http://www.portaldalinguaportuguesa.org/index.php?action=syllables&act=list

O seletor do indice alfabético é (#maintable a), sendo a propriedade href o alvo e a proriedade text o dado.

O seletor de próxima página é (#rollovertable + p > a) que contém o texto "seguintes", sendo a priedade href a navegação. A susência so nó com o o texto "seguintes" indica o fim dos dados para a letra.

## Fluxo de navegação

É feita uma requisição para o ponto entrada então o html é analisado para identificar as letras  através do seletor do indice alfabético. A análise deve gerar uma lista com os endereços (href) de casa letra, sendo esse lista considerado o ponto de entrada de cada letra.

Para cada item da lista de letras é feita a requisição e o conteúdo persisitdo conforme a convenção de armazenamento. O conteúdo então é analisado procurando endereço no seletor de próxima página que se encontrado se torna o ponto inicial para uma repetição do mesmo processo. Quando o seletor de próxima página não seja encontrado temmos indicação de término de processmento para o item da lista.





