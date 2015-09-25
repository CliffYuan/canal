##### 1.binlog ROW模式

****************************************************
* Batch Id: [2] ,count : [3] , memsize : [159] , Time : 2015-09-16 16:07:01
* Start : [mysql-bin.000004:49230:1442390790000(2015-09-16 16:06:30)]
* End : [mysql-bin.000004:49422:1442390790000(2015-09-16 16:06:30)]
****************************************************
==========================>entry start
================> binlog[mysql-bin.000004:49230] , executeTime : 1442390790000 , delay : 31596ms
 BEGIN ----> Thread id: 96
----------------> binlog[mysql-bin.000004:49363] , name[meizu_sms,T_SMS_USER] , eventType : INSERT , executeTime : 1442390790000 , delay : 31597ms
FID : 28    type=int(11)    update=true
FUSER_NAME : messagekkkkkk    type=varchar(20)    update=true
FPASSWORD : 8888888888    type=varchar(45)    update=true
----------------
 END ----> transaction id: 642
================> binlog[mysql-bin.000004:49422] , executeTime : 1442390790000 , delay : 31597ms
==========================>entry end
****************************************************
* Batch Id: [3] ,count : [3] , memsize : [165] , Time : 2015-09-16 16:12:20
* Start : [mysql-bin.000004:49449:1442391108000(2015-09-16 16:11:48)]
* End : [mysql-bin.000004:49647:1442391108000(2015-09-16 16:11:48)]
****************************************************
==========================>entry start
================> binlog[mysql-bin.000004:49449] , executeTime : 1442391108000 , delay : 32486ms
 BEGIN ----> Thread id: 96
----------------> binlog[mysql-bin.000004:49582] , name[meizu_sms,T_SMS_USER] , eventType : DELETE , executeTime : 1442391108000 , delay : 32486ms
FID : 10    type=int(11)
FUSER_NAME : XND999dddd    type=varchar(20)
FPASSWORD : HH88888888888888888    type=varchar(45)
----------------
 END ----> transaction id: 646
================> binlog[mysql-bin.000004:49647] , executeTime : 1442391108000 , delay : 32487ms
==========================>entry end


****************************************************
* Batch Id: [3] ,count : [3] , memsize : [166] , Time : 2015-09-24 10:17:42
* Start : [mysql-bin.000005:2519:1443061019000(2015-09-24 10:16:59)]
* End : [mysql-bin.000005:2718:1443061019000(2015-09-24 10:16:59)]
****************************************************
==========================>entry start
================> binlog[mysql-bin.000005:2519] , executeTime : 1443061019000 , delay : 43221ms
 BEGIN ----> Thread id: 65
----------------> binlog[mysql-bin.000005:2660] , name[meizu_sms,T_SMS_USER] , eventType : INSERT , executeTime : 1443061019000 , delay : 43221ms
FID : 205    type=int(11)    update=true
FUSER_NAME : 2015-09-23 22:16:59    type=varchar(20)    update=true
FPASSWORD : row    type=varchar(45)    update=true
----------------
 END ----> transaction id: 128
================> binlog[mysql-bin.000005:2718] , executeTime : 1443061019000 , delay : 43221ms
==========================>entry end


##### 2.binlog Mixed模式

****************************************************
* Batch Id: [4] ,count : [3] , memsize : [255] , Time : 2015-09-16 16:15:49
* Start : [mysql-bin.000004:49674:1442391317000(2015-09-16 16:15:17)]
* End : [mysql-bin.000004:49902:1442391317000(2015-09-16 16:15:17)]
****************************************************
==========================>entry start
================> binlog[mysql-bin.000004:49674] , executeTime : 1442391317000 , delay : 32062ms
 BEGIN ----> Thread id: 96
----------------> binlog[mysql-bin.000004:49747] , name[meizu_sms,] , eventType : INSERT , executeTime : 1442391317000 , delay : 32062ms
 sql ----> insert into T_SMS_USER(FID,FUSER_NAME,FPASSWORD)values(30,'messagekkkkkk','8888888888')
----------------
 END ----> transaction id: 649
================> binlog[mysql-bin.000004:49902] , executeTime : 1442391317000 , delay : 32062ms
==========================>entry end
****************************************************
* Batch Id: [5] ,count : [3] , memsize : [255] , Time : 2015-09-16 16:24:32
* Start : [mysql-bin.000004:49929:1442391840000(2015-09-16 16:24:00)]
* End : [mysql-bin.000004:50157:1442391840000(2015-09-16 16:24:00)]



****************************************************
* Batch Id: [2] ,count : [3] , memsize : [257] , Time : 2015-09-24 10:16:25
* Start : [mysql-bin.000005:2262:1443060942000(2015-09-24 10:15:42)]
* End : [mysql-bin.000005:2492:1443060942000(2015-09-24 10:15:42)]
****************************************************
==========================>entry start
================> binlog[mysql-bin.000005:2262] , executeTime : 1443060942000 , delay : 43369ms
 BEGIN ----> Thread id: 65
----------------> binlog[mysql-bin.000005:2343] , name[meizu_sms,] , eventType : INSERT , executeTime : 1443060942000 , delay : 43370ms
 sql ----> insert into T_SMS_USER(FID,FUSER_NAME,FPASSWORD)values(204,NOW(),'mixed')
----------------
 END ----> transaction id: 125
================> binlog[mysql-bin.000005:2492] , executeTime : 1443060942000 , delay : 43370ms
==========================>entry end


##### 3.binlog STATEMENT模式

****************************************************
==========================>entry start
================> binlog[mysql-bin.000004:49929] , executeTime : 1442391840000 , delay : 32283ms
 BEGIN ----> Thread id: 96
----------------> binlog[mysql-bin.000004:50002] , name[meizu_sms,] , eventType : INSERT , executeTime : 1442391840000 , delay : 32283ms
 sql ----> insert into T_SMS_USER(FID,FUSER_NAME,FPASSWORD)values(31,'messagekkkkkk','8888888888')
----------------
 END ----> transaction id: 652
================> binlog[mysql-bin.000004:50157] , executeTime : 1442391840000 , delay : 32283ms
==========================>entry end
****************************************************
* Batch Id: [6] ,count : [3] , memsize : [203] , Time : 2015-09-16 16:25:05
* Start : [mysql-bin.000004:50184:1442391874000(2015-09-16 16:24:34)]
* End : [mysql-bin.000004:50360:1442391874000(2015-09-16 16:24:34)]
****************************************************
==========================>entry start
================> binlog[mysql-bin.000004:50184] , executeTime : 1442391874000 , delay : 31950ms
 BEGIN ----> Thread id: 96
----------------> binlog[mysql-bin.000004:50257] , name[meizu_sms,] , eventType : DELETE , executeTime : 1442391874000 , delay : 31950ms
 sql ----> delete from T_SMS_USER where fid=31
----------------
 END ----> transaction id: 653
================> binlog[mysql-bin.000004:50360] , executeTime : 1442391874000 , delay : 31950ms
==========================>entry end

****************************************************
* Batch Id: [4] ,count : [3] , memsize : [261] , Time : 2015-09-24 10:18:44
* Start : [mysql-bin.000005:2745:1443061081000(2015-09-24 10:18:01)]
* End : [mysql-bin.000005:2979:1443061081000(2015-09-24 10:18:01)]
****************************************************
==========================>entry start
================> binlog[mysql-bin.000005:2745] , executeTime : 1443061081000 , delay : 43224ms
 BEGIN ----> Thread id: 65
----------------> binlog[mysql-bin.000005:2826] , name[meizu_sms,] , eventType : INSERT , executeTime : 1443061081000 , delay : 43224ms
 sql ----> insert into T_SMS_USER(FID,FUSER_NAME,FPASSWORD)values(206,NOW(),'statement')
----------------
 END ----> transaction id: 158
================> binlog[mysql-bin.000005:2979] , executeTime : 1443061081000 , delay : 43224ms
==========================>entry end
