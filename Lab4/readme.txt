1)  Alle 3 Dateien (kustomization.yaml, mysql-deployment.yaml, wordpress-deployment.yaml) in einem Ordner speichern

2)  Dann in diesem Ordner folgendes command ausführen:
    kubectl apply -k ./

3)  Nach ein paar Minuten:
    kubectl get all (-> EXTERNAL-IP von service/wordpress in Browser eingeben)

4) siehe: https://kubernetes.io/docs/tutorials/stateful-application/mysql-wordpress-persistent-volume/

