SUBDIRS = . codec session test

BUILT_SOURCES = HTTPCommonHeaders.h HTTPCommonHeaders.cpp

CommonHeadersGen: HTTPCommonHeaders.template.h HTTPCommonHeaders.template.gperf HTTPCommonHeaders.txt
	INSTALLED_GPERF=1 FBCODE_DIR=$(top_srcdir)/.. INSTALL_DIR=$(srcdir) ruby generate_http_gperfs.rb
	touch CommonHeadersGen

HTTPCommonHeaders.h: CommonHeadersGen

HTTPCommonHeaders.cpp: CommonHeadersGen

noinst_LTLIBRARIES = libproxygenhttp.la

libproxygenhttpdir = $(includedir)/proxygen/lib/http
nobase_libproxygenhttp_HEADERS = \
	HTTPCommonHeaders.h \
	HTTPConnector.h \
	HTTPConstants.h \
	HTTPException.h \
	HTTPHeaderSize.h \
	HTTPHeaders.h \
	HTTPMessage.h \
	HTTPMessageFilters.h \
	HTTPMethod.h \
	ProxygenErrorEnum.h \
	RFC2616.h \
	Window.h \
	codec/CodecDictionaries.h \
	codec/CodecProtocol.h \
	codec/ErrorCode.h \
	codec/FlowControlFilter.h \
	codec/HTTP1xCodec.h \
	codec/HTTPChecks.h \
	codec/HTTPCodec.h \
	codec/HTTPCodecFilter.h \
	codec/HTTPSettings.h \
	codec/SPDYCodec.h \
	codec/SPDYConstants.h \
	codec/SPDYUtil.h \
	codec/SPDYVersion.h \
	codec/SPDYVersionSettings.h \
	codec/SettingsId.h \
	codec/TransportDirection.h \
	codec/compress/GzipHeaderCodec.h \
	codec/compress/HPACKCodec.h \
	codec/compress/HPACKConstants.h \
	codec/compress/HPACKContext.h \
	codec/compress/HPACKDecodeBuffer.h \
	codec/compress/HPACKDecoder.h \
	codec/compress/HPACKEncodeBuffer.h \
	codec/compress/HPACKEncoder.h \
	codec/compress/HPACKHeader.h \
	codec/compress/Header.h \
	codec/compress/HeaderCodec.h \
	codec/compress/HeaderPiece.h \
	codec/compress/HeaderTable.h \
	codec/compress/Huffman.h \
	codec/compress/Logging.h \
	codec/compress/StaticHeaderTable.h \
	session/ByteEventTracker.h \
	session/ByteEvents.h \
	session/CodecErrorResponseHandler.h \
	session/HTTPDirectResponseHandler.h \
	session/HTTPDownstreamSession.h \
	session/HTTPErrorPage.h \
	session/HTTPEvent.h \
	session/HTTPSession.h \
	session/HTTPSessionAcceptor.h \
	session/HTTPSessionController.h \
	session/HTTPSessionStats.h \
	session/HTTPTransaction.h \
	session/HTTPTransactionEgressSM.h \
	session/HTTPTransactionIngressSM.h \
	session/HTTPUpstreamSession.h \
	session/SimpleController.h \
	session/TransportFilter.h

libproxygenhttp_la_SOURCES = \
	HTTPCommonHeaders.cpp \
	codec/CodecProtocol.cpp \
	codec/compress/GzipHeaderCodec.cpp \
	codec/compress/HeaderTable.cpp \
	codec/compress/HPACKCodec.cpp \
	codec/compress/HPACKContext.cpp \
	codec/compress/HPACKDecodeBuffer.cpp \
	codec/compress/HPACKDecoder.cpp \
	codec/compress/HPACKEncodeBuffer.cpp \
	codec/compress/HPACKEncoder.cpp \
	codec/compress/HPACKHeader.cpp \
	codec/compress/Huffman.cpp \
	codec/compress/Logging.cpp \
	codec/compress/StaticHeaderTable.cpp \
	codec/ErrorCode.cpp \
	codec/FlowControlFilter.cpp \
	codec/HTTP1xCodec.cpp \
	codec/HTTPChecks.cpp \
	codec/HTTPCodecFilter.cpp \
	codec/HTTPSettings.cpp \
	codec/SPDYCodec.cpp \
	codec/SPDYConstants.cpp \
	codec/SPDYUtil.cpp \
	codec/SettingsId.cpp \
	codec/TransportDirection.cpp \
	HTTPConnector.cpp \
	HTTPConstants.cpp \
	HTTPException.cpp \
	HTTPHeaders.cpp \
	HTTPMessage.cpp \
	HTTPMethod.cpp \
	ProxygenErrorEnum.cpp \
	RFC2616.cpp \
	session/ByteEvents.cpp \
	session/CodecErrorResponseHandler.cpp \
	session/HTTPDirectResponseHandler.cpp \
	session/HTTPDownstreamSession.cpp \
	session/HTTPErrorPage.cpp \
	session/HTTPEvent.cpp \
	session/HTTPSessionAcceptor.cpp \
	session/HTTPSession.cpp \
	session/HTTPTransaction.cpp \
	session/HTTPTransactionEgressSM.cpp \
	session/HTTPTransactionIngressSM.cpp \
	session/HTTPUpstreamSession.cpp \
	session/ByteEventTracker.cpp \
	session/SimpleController.cpp \
	session/TransportFilter.cpp \
	Window.cpp

libproxygenhttp_la_LIBADD = \
	../services/libproxygenservices.la \
	../ssl/libproxygenssl.la \
	../utils/libutils.la
