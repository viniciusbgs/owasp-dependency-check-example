# OWASP Dependency-Check Example

Este é um projeto simples para testar o uso da ferramenta [OWASP Dependency-Check](https://owasp.org/www-project-dependency-check/), que ajuda a identificar vulnerabilidades conhecidas em dependências de projetos.

## Pré-requisitos

Certifique-se de que você tem o seguinte instalado:

1. **Java** (JDK 8 ou superior)
2. **Apache Maven** (3.6 ou superior)
3. **OWASP Dependency-Check** (CLI ou plugin Maven)

## Passos para Testar

### 1. Clonar o Repositório

```bash
git clone https://github.com/viniciusbgs/owasp-dependency-check-example.git
cd owasp-dependency-check-example
```


### **2\. Executar o OWASP Dependency-Check**

#### **Opção 1: Usando o CLI do Dependency-Check**

1.  Baixe o [OWASP Dependency-Check CLI](https://github.com/jeremylong/DependencyCheck).
2.  Execute o comando:

```bash

dependency-check --project "owasp-dependency-check-example" \\

                 --scan . \\
                 --out dependency-check-report \\
                 --format ALL
```


Os relatórios serão gerados no diretório dependency-check-report/.

#### **Opção 2: Usando o Plugin Maven**

1.  Utilize o plugin Dependency-Check do pom.xml (já está feito no código do projeto):

```xml

<build>

    <plugins>

        <plugin>

            <groupId>org.owasp</groupId>

            <artifactId>dependency-check-maven</artifactId>

            <version>11.1.0</version>

            <executions>

                <execution>

                    <goals>

                        <goal>check</goal>

                    </goals>

                </execution>

            </executions>

        </plugin>

    </plugins>

</build>
```

2.  Execute o comando Maven:

```bash
mvn verify
```

Os relatórios serão gerados no diretório target/dependency-check-report/.

## **Visualizando Relatórios**

Abra o arquivo HTML gerado (por exemplo, target/dependency-check-report/dependency-check-report.html) em seu navegador para visualizar os resultados.
