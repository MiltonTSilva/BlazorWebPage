# Workflows com Github pages
## Este projeto foi realizado a fim de verificar e aplicar o workflows usando github pages

## Algumas considerações

- Quando criar seu arquivo .yml verificar os seguintes pontos.

  1. Sempre fique atendo ao nome da branch que está usando
  2. Para publicar um projeto blazor usar a opção -o docs pois é nesta pasta que o github irá guardar a publicação e não esquecer de colocar o nome do projeto

     exemplo:

         name: Publish .NET
     
         run: dotnet publish BlazorWebPage.csproj -c:Release -o docs --nologo
     
  3. Para efetuar o upload tem que especificar a pasta wwwwroot
    
        exemplo:
     
           name: Upload
            uses: actions/upload-pages-artifact@v3
            with:
            path: 'docs/wwwroot'
  4. No arquivo index.html deve ser alterado a url base para o caminho do github
 
       exemplo:
 
         original ==> <!--<base href="/" />-->
         alterado ==> <base href="https://miltontsilva.github.io/BlazorWebPage/" />
     O nome do repositório deve estar igual ao criado no github como no exemplo acima como "BlazorWebPage" respeitando Maiúsculas e Minúsculas.


     
