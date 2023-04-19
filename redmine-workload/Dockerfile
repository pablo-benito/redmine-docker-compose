FROM redmine:5.0.5

USER redmine
ENV REDMINE_ROOT=/usr/src/redmine
ENV PURPLE_MINE2_VERSION=2.15.0

# The main branch currently do not support redmine 5.x
RUN echo "Installing workload plugin" && \
	cd ${REDMINE_ROOT}/plugins && \
	git clone https://github.com/xmera-circle/redmine_workload && \
	echo "Switch to develop branch" && \
	cd ${REDMINE_ROOT}/plugins/redmine_workload && \
	git checkout develop

RUN echo "Installing purple2 theme" && \
    cd ${REDMINE_ROOT}/public/themes/ && \
    wget -qO- https://github.com/mrliptontea/PurpleMine2/archive/refs/tags/v${PURPLE_MINE2_VERSION}.tar.gz \
    	| tar xvz
	
