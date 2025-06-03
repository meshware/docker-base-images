version=21.0.6

create-multi-arch-builder:
	docker buildx create --name=mybuilder --driver docker-container --platform linux/amd64,linux/arm64

image-oracle-jdk-21:
	docker buildx build --builder mybuilder --platform linux/amd64,linux/arm64 -t hurdes/ubuntu-oracle-jdk:${version} -f ./Dockerfile --push .

push-oracle-jdk-21:
	docker push hurdes/ubuntu-oracle-jdk:${version}