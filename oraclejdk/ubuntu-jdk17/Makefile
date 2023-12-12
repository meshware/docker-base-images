version=17.0.9

create-multi-arch-builder:
	docker buildx create --name=mybuilder --driver docker-container --platform linux/amd64,linux/arm64

image-oracle-jdk-17:
	docker buildx build --builder mybuilder --platform linux/amd64,linux/arm64 -t hurdes/ubuntu-oracle-jdk:${version} -f ./Dockerfile --push .

push-oracle-jdk-17:
	docker push hurdes/ubuntu-oracle-jdk:${version}