# goit-argo

GitOps-репозиторій для автоматичного розгортання Kubernetes-ресурсів через Argo CD `ApplicationSet`.

## Структура

```text
namespace/
├── application/
│   ├── demo-nginx.yaml
│   └── ns.yaml
└── infra-tools/
    └── ns.yaml
```

`ApplicationSet` відстежує директорії `namespace/*` і створює окремий Argo CD Application для кожної директорії.

Після змін у маніфестах необхідно виконати:

```bash
git add .
git commit -m "опис змін"
git push origin main
```

Argo CD автоматично підхопить зміни та синхронізує їх з EKS-кластером.

Terraform-проєкт: [goit-devops-hw-07](https://github.com/Matvieienko/goit-devops-hw-07)