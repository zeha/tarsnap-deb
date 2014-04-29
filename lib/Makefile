LIB	=	tarsnap
WARNS	?=	6
CFLAGS	+=	-DPLATFORM_CONFIG_H=\"config_freebsd.h\"
CFLAGS	+=	-DTSSERVER=\"${TSSERVER}\"
CFLAGS	+=	-I ../tar

# Crypto code
.PATH	:	crypto
SRCS	+=	crypto_file.c
SRCS	+=	crypto_hash.c
SRCS	+=	crypto_keys.c
SRCS	+=	crypto_keys_server.c
SRCS	+=	crypto_keys_subr.c
SRCS	+=	crypto_passwd_to_dh.c
SRCS	+=	crypto_rsa.c
SRCS	+=	crypto_scrypt-nosse.c
SRCS	+=	crypto_session.c
CFLAGS	+=	-I crypto

# Data structures
.PATH	:	datastruct
SRCS	+=	rwhashtab.c
SRCS	+=	patricia.c
CFLAGS	+=	-I datastruct

# Key file handling code
.PATH	:	keyfile
SRCS	+=	keyfile.c
CFLAGS	+=	-I keyfile

# Tarsnap request-response protocol code
.PATH	:	netpacket
SRCS	+=	netpacket_delete.c
SRCS	+=	netpacket_directory.c
SRCS	+=	netpacket_hmac.c
SRCS	+=	netpacket_op.c
SRCS	+=	netpacket_read.c
SRCS	+=	netpacket_register.c
SRCS	+=	netpacket_transaction.c
SRCS	+=	netpacket_write.c
CFLAGS	+=	-I netpacket

# Tarsnap client-server code
.PATH	:	netproto
SRCS	+=	netproto.c
SRCS	+=	netproto_connect.c
SRCS	+=	netproto_keyexchange.c
SRCS	+=	netproto_packet.c
CFLAGS	+=	-I netproto

# Non-blocking network routines
.PATH	:	network
SRCS	+=	tsnetwork_buf.c
SRCS	+=	tsnetwork_bwlimit.c
SRCS	+=	tsnetwork_connect.c
SRCS	+=	tsnetwork_cork.c
SRCS	+=	tsnetwork_register.c
SRCS	+=	tsnetwork_select.c
SRCS	+=	tsnetwork_sleep.c
SRCS	+=	tsnetwork_writeq.c
CFLAGS	+=	-I network

# scryptenc code
.PATH	:	scryptenc
SRCS	+=	scryptenc.c
SRCS	+=	scryptenc_cpuperf.c
CFLAGS	+=	-I scryptenc

# Utility code
.PATH	:	util
SRCS	+=	dirutil.c
SRCS	+=	getfstype.c
SRCS	+=	hexlink.c
SRCS	+=	memlimit.c
SRCS	+=	sigquit.c
SRCS	+=	tvmath.c
CFLAGS	+=	-I util

### Bits from libcperciva
# Fundamental algorithms
.PATH	:	../libcperciva/alg
SRCS	+=	sha256.c
CFLAGS	+=	-I ../libcperciva/alg

# Crypto code
.PATH	:	../libcperciva/crypto
SRCS	+=	crypto_aesctr.c
SRCS	+=	crypto_dh.c
SRCS	+=	crypto_dh_group14.c
SRCS	+=	crypto_entropy.c
SRCS	+=	crypto_verify_bytes.c
CFLAGS	+=	-I ../libcperciva/crypto

# Data structures
.PATH	:	../libcperciva/datastruct
SRCS	+=	elasticarray.c
SRCS	+=	ptrheap.c
SRCS	+=	timerqueue.c
CFLAGS	+=	-I ../libcperciva/datastruct

# Events code
.PATH	:	../libcperciva/events
SRCS	+=	events.c
SRCS	+=	events_immediate.c
SRCS	+=	events_network.c
SRCS	+=	events_network_selectstats.c
SRCS	+=	events_timer.c
CFLAGS	+=	-I ../libcperciva/events

# Network code
.PATH	:	../libcperciva/network
SRCS	+=	network_accept.c
SRCS	+=	network_buf.c
SRCS	+=	network_connect.c
CFLAGS	+=	-I ../libcperciva/network

# Utility code
.PATH	:	../libcperciva/util
SRCS	+=	asprintf.c
SRCS	+=	b64encode.c
SRCS	+=	entropy.c
SRCS	+=	hexify.c
SRCS	+=	humansize.c
SRCS	+=	monoclock.c
SRCS	+=	readpass.c
SRCS	+=	sock.c
SRCS	+=	sock_util.c
SRCS	+=	warnp.c
CFLAGS	+=	-I ../libcperciva/util

# Compiler flags for profiling
.if defined(PROFILE)
CFLAGS	+=	-g -pg -DPROFILE
.else
NO_PROFILE=	YES
.endif

# Debugging flags
.if defined(DEBUG)
CFLAGS	+=	-g
CFLAGS	+=	-DDEBUG
.endif

.include <bsd.lib.mk>
