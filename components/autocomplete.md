# Componentes / AutocompleteComponent

## **Descrição**
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Componente padrão de _autocomplete_ do sistema. Foi desenvolvido de forma a encapsular e adaptar para o sistema as funcionalidades do componente de _autocomplete_ (_typeahead_) do framework _ngx-bootstrap_ na versão [4.2.0](https://valor-software.com/ngx-bootstrap/old/4.2.0/#/typeahead).

## **Inputs**
| Nome                            | Tipo      | Valor padrão | Obrigatório |Descrição                                                                                |
|---------------------------------|-----------|--------------|-------------|-----------------------------------------------------------------------------------------|
| opcaoCampo                      | String    | vazio        |     S       |Deve ser informado aqui o campo dos objetos na lista que será utilizado para exibir o valor da opção.         |
| placeholder                     | String    | vazio        |     N       |Exibe internamente ao campo um texto informativo.                                        |
| labelCampo                      | String    | vazio        |     N       |O nome que será exibido acima do campo. Também é utilizado para criar o **id** do campo. |
| name                            | String    | vazio        |     S       |Utilizado para identificar o campo no formulário ao qual ele pertence.                   |
| parenteForm                     | FormGroup | null         |     S       |Recebe todo o formulario pai ao qual este campo pertence.                                |
| mostrarLabel                    | boolean   | true         |     N       |Informa se o campo deve exibir ou não o label acima do campo.                            |
| maxlength                       | number    | 255          |     N       |Informa a quantidade maxima de caracteres suportado pelo campo.                          |
| desabilitarErroNenhumResultado  | boolean   | false        |     N       |Torna opcional se o campo sem opções localizadas deve ser marcado como inválido.         |
| desabilitarCampo                | boolean   | false        |     N       |Desabilita o campo de acordo com o parâmetro recebido.                                   |
| urlRequisicao                   | String    | vazio        |     S       |A _URL_ de requisião que o autocomplete usara para buscar dados na _API REST_.           |
| objetoRequisicaoPOST            | any       | null         |     N       |Deve ser utilizado caso o usuário queira passar um objeto na requisão ao _backend_.      |

## **Exemplos**
1. Implementação simples
   
   Template:
    ```html
        <is-autocomplete
          [opcaoCampo]="'label'"
          [labelCampo]="'Medicamento'"
          [parenteForm]="formulario"
          [name]="'medicamento'"
          [urlRequisicao]="listarMedicamentos()"
          (objetoSelecionado)="setMedicamento($event)">
        </is-autocomplete>
    ```

    Componente:
    ```typescript

        // Formulário utilizado que contém e controla o campo
        this.formulario = new FormGroup({
            medicamento: new FormControl('')
        });

        // Cria a URL de requisição usada pelo autocomplete para buscar o itens que serão exibidos
        listarMedicamentos() {
            return this.conexaoResource.baseUrl(`shared/medicamentos`);
        }

        // Recebe o objeto que foi selecionado
        setMedicamento(medicamento: any) {
            this.medicamento = medicamento;
        }
    ```