# Kubernetes
 [Kubernetes](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/) ou K8S em palavras bem simples são agrupamento de aplicações executados em conteineres, o kubernetes fica responvasável em gerenciar esses clusters de host com facilidade e eficiência.
 
# Arquitetura do Kubernetes
O cluster kubernetes tem 2 componentes principais: 
- **Master node ou Control plane**
- **Worker nodes**

## Master node ou Control plane
O master node é o centro nervoso de cada cluster do kubernetes. Ele é responsável para que o cluster do kubernetes atinja um estado desajado defino pelo usuário. O master node interage com nodes usando o kubelet.<br> 
Master node é composto pelo seguinte componentes:
- **kube-apiserver:** Fornece uma API que serve como front-end de um control plane do kubernetes. As solicitações externas e internas é de sua responsábilidade de determinar se a solicitação é válida  e processa-la. O kubectl command-line interface(CLI) ou outra ferramenta como kubeadm batem ma API do kube-apiserver. Resumindo kube-apiserver é o responvável por estabelecer a comunicação entre o usuário, elemento exeterno e componentes de cluster, como pods, ConfigMaps, events e namespaces.

- **kube-scheduler:** É responsável atribuir pods em nodes especificos. Ele usára informações como soliticação de computação e limites de cargas de trablho para atribuir adequadamente sua carga de trabalho em um node específico.

- **kube-controller-manager:** É o gerenciador do kubernetes é ele monitora e regula o estado do cluster kubernetes.
Ele recebe informações sobre o estado atual do cluster e faz alterações para direcionar o status do cluster para o estado desejado. Kube-controller-manager é responsável pelo controle de replicas.

- **etcd:** Este componente é responsável por salvar o estado e as configurações do cluster kubernetes em formato de chave e valor.
