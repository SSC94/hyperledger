## 준비물 생성
  crypto-comfig.yaml
  configtx.yaml
  generate.sh
  crypto-config dir
  config/ gen.bk, ch.tx

##네트워크 구성
docker-compose.yml
docker-compose -> up
ca, peerx3, cdbx3, orderer, cli(설치,배포한다. 연결정보,인증서,sdk,peer가 있다.)
net basic

채널 생성
cli ch.tx
peer channel create
mychannel.block
각 피어별로 peer channel join

체인 코드
go,java,nodejs
shim(데이터를 가져오거나 저장, getState-putState),
peer(chaincode를 수행하고 리턴도 받는다, blockchain data-world state-private data),
contract(계약사항의 기본적인 함수를 가진다.init(), invoke() )
설치->피어, 배포->채널, 테스트


images; 1.4.7 ca peer orderer tools couchdb
fabric bin: cryptogen configtxgen -> 환경변수
fabric-samples;

유틸리티 nodejs docker docker-compose curl apt-get tar vi nano go git code

linux ubuntu 18.04 LTS

docker 설정(docker에 관해 궁금한 것은 공식사이트 참고하자,도커 책도 좋음 얇거나 실전프로젝트책)
 - network 이름 basic
 - 서비스 설정 
  ` images
  ` 환경변수
  ` 포트포워팅
  ` 시작디렉토리
  ` 시작명령
  ` 공유폴더

chaincode는 피어에서 작동 channel에 저장 api로 사용(cli도 api) 
api(web server)- connection.json, 인증서, argument(function name, args)
chaincode는 블록체인의 tx를 저장하기 위해 쓴다. peer가 chaincode를 invoke(불러오기)한다.
putstate는 worldstate에 data를 넣는것이고, getstate는 data를 읽는 것이다.
shim.GetStateByRange("a","z") a에서 z까지 첫글자 정보만 읽는다.
cc.sh로 테스트를 해본다.(실행할때 ./를 붙이자)
instantiate은 처음 deploy할 때 쓰고, 다음에는 upgrade와 version숫자를 바꿔서 하자
