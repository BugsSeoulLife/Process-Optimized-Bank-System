# Bank-System

<img width="200" height="150" alt="image" src="https://user-images.githubusercontent.com/26247241/190343124-a1b24a6d-3515-454b-bb59-daa6e697e661.png"><img width="200" height="150" alt="image" src="https://user-images.githubusercontent.com/26247241/190343174-0723632a-96a3-40b6-8a13-b67b2efd4fe0.png">


timespent : 2015.04~06

tech : VirtualBox CentOS LINUX, C

functions : CPU-scheduling(RR,FCFS), multi-threading(entrance,service), mutex
 
content : 고객의 10만 명의 정보를 은행 system에서 미리 알고 있는 것이 아니라 입장할 때 아는 것 이므로, 고객들의 정보를 queue사이즈로 정했고, 무한정 size로 지정한 다. 서비스는 계속해서 제공되며 쉬는 시간 없이 진행하였다. 10만 명이 서비스를 받게되면 은행은 서비스를 멈춘다. 즉, 입장하는 고객들의 수는 10만명 이상일 수 있다. 입장 후 에 time out으로 대기열에서 나가는 고객들도 있기 때문이다.
자본금 1억으로 설정하였다. 동일 은행 내에서 이체를 하도록 설정하였으며 고객 이 입금을 했을 시 자본금이 증가하고, 이체할 때 자본금이 감소한다. 또한 이체는 동일한 은행 내에서만 이체하도록 설정하여서 자본금은 감소하지 않고 되뢰어 이체 율을 1%로 측정하여서 자본금이 고객이 이체하려는 금액x0.01만큼 증가한다. 은행 이 행여나 파산을 하게되면 어쩌나 걱정을 하였지만, random변수들을 잘 구현하여 서 파산이 되지않도록 구현하였다. 대기시간은 30-60초로 설정하였다. 즉, 대기시간만큼 고객이 기다리면 time out이 되어서 고객이 대기 열에서 나가게 된다. 또한 60-90초면 고객의 대기시간이 길면 입장 thread에서 서비스 thread로 잘 넘어가지 않는다. 서비스 시간은 5-9초정도 로 설정하였다. CPU별로 실행속도가 달랐다. laptop1에서는 7분가량의 평균이 나왔고 laptop2에 서는 40초의 시간이 나왔다. 그 이유는 CPU의 성능의 차이 떄문 이라고 생각했다. 그래서 성능이 더 좋은 CPU의 결과를 채택하였다.
