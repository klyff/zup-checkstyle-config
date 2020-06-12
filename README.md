Configuração do Zup Checkstyle
================================


Este projeto fornece uma configuração padrão para o estilo de verificação de códigos da Zup.

Para usá-lo, configure seu maven-checkstyle-plugin da seguinte maneira:

`` ``
   <plugin>
     <artifactId> maven-checkstyle-plugin </artifactId>
     <versão> 2.17 </ versão>
     <dependências>
       <dependência>
         <groupId> com.spotify.checkstyle </groupId>
         <artifactId> spotify-checkstyle-config </artifactId>
         <versão> ÚLTIMA VERSÃO </version>
       </dependency>
       <dependência>
         <groupId> com.puppycrawl.tools </groupId>
         <artifactId> checkstyle </artifactId>
         <versão> 8.24 </ versão>
       </dependency>
     </dependencies>
     <configuração>
       <configLocation> spotify_checks.xml </configLocation>
       
       <! - Os seguintes parâmetros são opcionais: ->
       <consoleOutput> true </consoleOutput>
       <failOnViolation> true </failOnViolation>
       <logViolationsToConsole> true </logViolationsToConsole>
       erro <violationSeverity> </violationSeverity>
     </configuration>
     <execuções>
       <execução>
         <id> validar </id>
         <phase> validar </phase>
         <objetivos>
           <goal> verifique </goal>
         </goals>
       </execution>
     </executions>
   </plugin>
`` ``

Consulte os [documentos do maven-checkstyle-plugin] (https://maven.apache.org/plugins/maven-checkstyle-plugin/check-mojo.html) 
para obter mais informações sobre o significado dos parâmetros de configuração.

Internamente, temos a configuração acima na seção `<pluginManagement />` de um 
pom principal da Zup, o que significa que os projetos precisam apenas especificar o seguinte em seus
Seção `<build> <plugins>`:

`` ``
   <plugin>
      <artifactId> maven-checkstyle-plugin </artifactId>
   </plugin>
`` ``

# Configuração

## Supressões

A configuração do plugin checkstyle que você obtém de `zup_checks.xml` diz para 
opcionalmente, procure um arquivo chamado `suppressions.xml`, conforme
[Documentos do SuppressionFilter] (http://checkstyle.sourceforge.net/config_filters.html#SuppressionFilter). 
Isso significa que você pode configurar supressões fornecendo esse arquivo no seu
caminho de classe do projeto ou no diretório atual em que você o constrói - note 
para projetos com vários módulos, provavelmente é uma boa ideia usar algo
como [esta solução] (http://stackoverflow.com/a/19690484/1659929) para compartilhar
a configuração entre cada submódulo.

# IDEA support

Há um [arquivo de configuração para o IntelliJ IDEA] (src / main / idea / zup-checkstyle-idea.xml) que você pode importar para o seu projeto.

# Código de conduta
Este projeto segue o [Código de Conduta Aberto] [código de conduta]. Ao participar, espera-se que você respeite esse código.

[código de conduta]: https://github.com/klyff/zup-code-of-conduct/blob/master/code-of-conduct.md