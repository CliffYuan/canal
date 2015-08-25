##### 解析流程
CanalEntry.Entry由3部分组成:
{
CanalEntry.Header,
CanalEntry.EntryType,
CanalEntry.ByteString
}

##### 1.阻塞接收数据
DirectLogFetcher.fetch0(){ channel.read(buffer);}没有数据时候,阻塞在止.

##### 2.接收到数据流程
1)
int netlen = getUint24(PACKET_LEN_OFFSET);//62
int netnum = getUint8(PACKET_SEQ_OFFSET);//5
TableMapLogEvent

TableMapLogEvent解析成CanalEntry.Entry==null

2)
int netlen = getUint24(PACKET_LEN_OFFSET);//52
int netnum = getUint8(PACKET_SEQ_OFFSET);//6
WriteRowsLogEvent

EntryType=ROWDATA

3)
XidLogEvent
EntryType=TRANSACTIONEND
会调用flush(),投递消息到eventStore中



