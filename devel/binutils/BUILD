./configure  --prefix=/usr    \
             --disable-werror \
             $OPTS         &&

make tooldir=/usr          &&
prepare_install            &&
make tooldir=/usr install  &&
make tooldir=/usr install-info  &&
mkdir -p $DOCUMENT_DIRECTORY/binutils  &&
cp -p binutils/NEWS binutils/ChangeLog $DOCUMENT_DIRECTORY/binutils &&

# For some reason installwatch fail to pick up the ld hardlink, touching it solves that issue
if [ -e /usr/bin/ld ]; then
  touch /usr/bin/ld
fi
