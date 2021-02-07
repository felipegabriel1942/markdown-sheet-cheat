# Componentes / AutocompleteComponent

## **Descrição**
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Componente padrão de _autocomplete_ do sistema. Foi desenvolvido de forma a encapsular e adaptar para o sistema as funcionalidades do componente de _autocomplete_ (_typeahead_) do framework _ngx-bootstrap_ na versão [4.2.0](https://valor-software.com/ngx-bootstrap/old/4.2.0/#/typeahead).

## **Inputs**
| Nome         | Tipo      | Valor padrão | Descrição |
|--------------|-----------|--------------|-----------|
| opcaoCampo   | String    | vazio        | Deve ser informado aqui o campo que será utilizado para exibir o valor da opção.|
| placeholder  | String    | vazio        | Exibe internamente ao campo um texto informativo. |
| labelCampo   | String    | vazio        | O nome que será exibido acima do campo. Também é utilizado para criar o **id** do campo.|
| name         | String    | vazio        | Utilizado para identificar o campo no formulário ao qual ele pertence.|
| parenteForm  | FormGroup | null         | Recebe todo o formulario pai ao qual este campo pertence.|
| mostrarLabel | boolean   | true         | Informa se o campo deve exibir ou não o label acima do campo.|
| maxlength    | number    | 255          | Informa a quantidade maxima de caracteres suportado pelo campo.|
| desabilitarErroNenhumResultado    | boolean    | false          | Torna opcional se o campo sem opções localizadas deve ser marcado como inválido.|
| desabilitarCampo    | boolean    | false          | Desabilita o campo de acordo com o parâmetro recebido.|
| urlRequisicao    | String    | vazio          | A _URL_ de requisião que o autocomplete usara para buscar dados na _API REST_.|
| objetoRequisicaoPOST    | any    | null          | Deve ser utilizado caso o usuário queira passar um objeto na requisão ao _backend_.|
| objetoRequisicaoPOST    | any    | null          | Deve ser utilizado caso o usuário queira passar um objeto na requisão ao _backend_.|