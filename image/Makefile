.PHONY: build

# Current apache hive releases: http://hive.apache.org/releases.html

HBASE_VERSION = 2.1.7
HIVE_VERSION = 3.1.2

DOCKER = docker
DOCKER_REPO = chenseanxy/hive

all: build

### Build hive versioned images with native libs.
build:
	$(DOCKER) build -t hive:$(HIVE_VERSION)-hbase$(HBASE_VERSION) \
	--build-arg VERSION=$(HIVE_VERSION) \
	.

tag: 
	$(DOCKER) tag \
	hive:$(HIVE_VERSION)-hbase$(HBASE_VERSION) \
	$(DOCKER_REPO):$(HIVE_VERSION)-hbase$(HBASE_VERSION)

push: 
	$(DOCKER) push $(DOCKER_REPO):$(HIVE_VERSION)-hbase$(HBASE_VERSION)

### Fetch binary distribution
apache-hive-%-bin.tar.gz:
	curl -LO http://archive.apache.org/dist/hive/hive-$(HIVE_VERSION)/apache-hive-$(HIVE_VERSION)-bin.tar.gz

### TODO: Fetch mysql java connector here
mysql-java-connector.jar:
	echo "Please download mysql java connector"

# Keep intermediate downloads.
.PRECIOUS: apache-hive-%-bin.tar.gz
