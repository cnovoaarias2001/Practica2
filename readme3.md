**1º Comproba que a tes a imaxe httpd** 
Comprobo que teño a imaxen httpd co comando `docker images`.

**2º Crea un contenedor de nome 'asir_httpd'.** 
Creo un contenedor de nome "sir_httpd" co comando `docker run -d --name asir_httpd httpd`.

**3º Mapea o porto 80 do contenedor có 8080 da túa máquina.** Para poder mapear o porto 80 do conenedor debemos borrar o contenedor e facelo de nuevo añadiendo o parámetro `-p 8080:80` e ``-v /home/carlos/htdocs:/usr/local/apache2/htdocs/` para montarlo directamente no noso directorio htdocs.

**Comando final** `docker run -d --name asir_httpd -p 8080:80 -v /home/carlos/htdocs:/usr/local/apache2/htdocs/ httpd`.

**4º Mostra unha páxina html aloxada no apache2 dende o teu navegador.** 
Co URL `localhost:8080` a utilizamos en calquera navegador e veremos a páxina.

**5º Crea un contenedor 'asir_web1' que use este mesmo directorio para 'htdocs' e o puerto 8000**
Para crear o contenedor e igual que antes pero cambiando o nome do contenedor e en vez de utilizar o porto 8080 utilizamos o 8000: `docker run -d --name asir_web1 -p 8000:80 -v /home/carlos/htdocs:/usr/local/apache2/htdocs/ httpd`

**6º Crea outro contenedor 'asir_web2' có el mesmo directorio e otro puerto, como o 8090.** 
E utilizamos o mesmo comando que antes pero cambiando o que nos pide: `docker run -d --name asir_web2 -p 8090:80 -v /home/carlos/htdocs:/usr/local/apache2/htdocs/ httpd`

Para comprobar que as duas paxina mostran o mesmo cas URLs `localhost:8090` e `localhost:8000`.