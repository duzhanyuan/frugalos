##
## FrugalOSビルド用のベースイメージ
##
FROM centos:7

##
## yumパッケージ群をインストール
##
RUN yum -y install gcc automake libtool vim git make patch

##
## Rustをインストール
##
RUN curl https://sh.rustup.rs -sSf > rustup.sh && sh rustup.sh -y
ENV PATH $PATH:/root/.cargo/bin

##
## Frugalosをビルド
##
RUN git clone https://github.com/frugalos/frugalos.git
# Note: https://github.com/frugalos/frugalos/releases/tag/0.11.0
RUN cd frugalos && git checkout 0.11.0 && cargo build --release --all
