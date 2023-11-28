# AWS-ECS-Pipepline

# Tutorial: Amazon ECS-Standardbereitstellung mit CodePipeline

- Ein Source-Control-Repository (dieses Tutorial verwendet CodeCommit) mit Ihrer Dockerfile und Anwendungsquelle. 
  Weitere Informationen finden Sie im AWS CodeCommitBenutzerhandbuch unter Erstellen eines CodeCommit Repositorys.

- Ein Docker-Image-Repository (dieses Tutorial verwendet Amazon ECR), das ein Image enthält, 
  das Sie aus Ihrem Dockerfile und Ihrer Anwendungsquelle erstellt haben. 
  Weitere Informationen finden Sie unter Creating a Repository and Push an Image im Amazon Elastic Container Registry User Guide.

- Eine Amazon ECS-Aufgabendefinition, die auf das in Ihrem Image-Repository gehostete Docker-Image verweist. 
  Weitere Informationen finden Sie unter Erstellen einer Aufgabendefinition im Amazon Elastic Container Service Developer Guide.

  # Wichtig
Die Amazon ECS-Standardbereitstellungsaktion für CodePipeline erstellt eine eigene Revision der Aufgabendefinition auf der Grundlage der vom Amazon ECS-Service verwendeten Revision. Wenn Sie neue Versionen für die Aufgabendefinition erstellen, ohne den Amazon ECS-Service zu aktualisieren, werden diese Revisionen bei der Bereitstellungsaktion ignoriert.


 # buildx-Plugin für Docker installiert 

    docker buildx create --use

- Dieser Befehl erstellt und setzt einen Standard-Builder für buildx

  # Erstellen eine Image
   
   - docker build --platform linux/amd64 -t my-pipeline-image .

   # um einen Container zu erstellen und auszuführen

    - docker run --rm -it -p 8080:80 --name my-pipeline-image:latest

