# Kubernetes
 [Kubernetes](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/) ou K8S em palavras bem simples são agrupamento de aplicações executados em conteineres, o kubernetes fica responvasável em gerenciar esses clusters de host com facilidade e eficiência.
 
# Arquitetura do Kubernetes
O cluster kubernetes tem 2 componentes principais: 
- **Master node ou Control plane**
- **Worker nodes**

## Master node ou Control plane
O master node é o centro nervoso de cada cluster do kubernetes. Ele é responsável para que o cluster do kubernetes atinja um estado desajado definido pelo usuário. O master node interage com nodes usando o kubelet.<br> 
Master node é composto pelo seguinte componentes:
- **kube-apiserver:** Fornece uma API que serve como front-end de um control plane do kubernetes. As solicitações externas e internas é de sua responsábilidade de determinar se a solicitação é válida  e processa-la. O kubectl command-line interface(CLI) ou outra ferramenta como kubeadm batem ma API do kube-apiserver. Resumindo kube-apiserver é o responvável por estabelecer a comunicação entre o usuário, elemento exeterno e componentes de cluster, como pods, ConfigMaps, events e namespaces.

- **kube-scheduler:** É responsável atribuir pods em nodes especificos. Ele usára informações como soliticação de computação e limites de cargas de trablho para atribuir adequadamente sua carga de trabalho em um node específico.

- **kube-controller-manager:** É o gerenciador do kubernetes é ele monitora e regula o estado do cluster kubernetes.
Ele recebe informações sobre o estado atual do cluster e faz alterações para direcionar o status do cluster para o estado desejado. Kube-controller-manager é responsável pelo controle de replicas.

- **etcd:** Este componente é responsável por salvar o estado e as configurações do cluster kubernetes em formato de chave e valor.


<img src="https://github.com/kadeguilherme/k8s-basico/blob/main/images/k8s-arquitetura-master.png" >

## Componentes do Node
Abaixo estão os principais componentes encontrado em um node(Worker).

- **pods:** Em resumo o pod é um encapsulamento dos contêineres.
- **kubelet:** Cada node contém um kubelet, que é o responsável pela comunicação com kube-controller-manager.
- **kube-proxy:** É o responsável em pela rede dos nós. É ele que permitem a comunicação de rede com seus pods.


Vou deixar um link de um artigo que trás mais detalhes de todos componentes do Master e Node.
[Artigo](https://vertigo.com.br/kubernetes-6-principais-componentes-da-sua-arquitetura/)

<img src="https://github.com/kadeguilherme/k8s-basico/blob/main/images/architecture-nodes.svg">

# Objetos
Objetos k8s descrevem o estado do seu cluster e são representado por arquivos JSON ou YAML.
Por exemplo, ao criar um objeto Deployment, o k8s garante que numero especificado de replicas esteja sempre em execução mesmo se o cluster for renicializado.

Existe duas categoria de objetos do kubernetes:
- basic-object
- high-level objects

# Workload
Workloas são objetos que defenir regras para os pods. Por exempleo voce tem 3 pods rodando uma aplicação na versão stable, e com isso a versão será atualizada para lastet,sem a utilização do Deployments, que é um tipo de Worload, para ocorrer essa atualização necessita à destruição dos pods e a criação com a nova versão feita de forma manual. No entanto, para torna a nossa vida consderavelmente mais fácil, você não precisa gerenciar cada Pod. Em vez disso podemos utilizar o Deployment para gerenciar nossos pods.
O kubernetes fornece vários recursos de workload intregados:
- ReplicaSet
- Deployment
- StatefulSet
- DaemonSet
- Job
- CronJob
- Namespace
