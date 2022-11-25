version=11-jre

image-openjdk-jre-11:
	docker build --platform linux/amd64 -t hurdes/openjdk:${version} -f ./Dockerfile .

push-openjdk-jre-11:
	docker push hurdes/openjdk:${version}
