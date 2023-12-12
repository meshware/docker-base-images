version=11.0.21

create-multi-arch-builder:
	docker buildx create --name=mybuilder --driver docker-container --platform linux/amd64,linux/arm64
	
image-oracle-jdk-11:
	docker buildx build --builder mybuilder --platform linux/amd64,linux/arm64 -t hub.jdcloud.com/jmsf/ubuntu-oracle-jdk:${version} -f ./Dockerfile --push .

push-oracle-jdk-11:
	docker push hurdes/ubuntu-oracle-jdk:${version}