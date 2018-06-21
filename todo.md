

Addon firefox : (et chrome)
 
Cookies Manager+
Firebug

Temper data
Burp suite
InformEnter
Live HTTP headers
User Agent Switcher
View Source Charte $(version)

No script

Site :
	duckduckgo.com

model OWASP

FAIL FOUND ::

[1] redirection sur facebook  			=> FLAG : [B9E775A0291FED784A2D9680FCFAD7EDD6B8CDF87648DA647AAF4BBA288BCAB3]

[2] Injection Sql member  				=> FLAG : [4A474D7856BE3C7FCB262B8E2E931E20FC8EC61FEBD184F40D5D0452C291ED22]

[3] Fail XSS : page feedback 			=> FLAG : [df2eb4ba34ed059a1e3e89ff4dfc13445f104a1a52295214def1c4fb1693a5c3]

[4] FAIL recover mot de pass 			=> FLAG : [1D4855F7337C0C14B6F44946872C4EB33853F40B2D54393FBE94F49F1E19BBB0]

[5] Signin brut force 					=> FLAG : [b3a6e43ddf8b4bbb4125e5e7d23040433827759d4de1c04ea63907479a80a6b2]

[6] Transversal directory 				=> FLAG : [b12c4b2cb8094750ae121a676269aa9e2872d07c06e429d25a63196ec1c8c1d0]

[7] Robots.txt 							=> FLAG : [d19b4823e0d5600ceed56d5e896ef328d7a2b9e7ac7e80f4fcdb9b10bcb3e7ff]

[8] Injection Sql image 				=> FLAG : [f2a29020ef3132e01dd61df97fd33ec8d7fcd1388cc9601e7db691d17d4d6188]

[9] Fail Upload  						=> FLAG : [46910d9ce35b385885a9f7e2b336249d622f29b267a1771fbacf52133beddba8]

[10] Survey 							=> FLAG : [03A944B434D5BAFF05F46C4BEDE5792551A2595574BCAFC9A6E25F67C382CCAA]

[11] User agent 						=> FLAG : [F2A29020EF3132E01DD61DF97FD33EC8D7FCD1388CC9601E7DB691D17D4D6188]

[12] Hide Url. 							=> http://192.168.9.128/.hidden/ ya forcement quelque chose dans ce truc

[13] XSS forgot password 				=> FLAG : [1d4855f7337c0c14b6f44946872c4eb33853f40b2d54393fbe94f49f1e19bbb0]

[14] Faille Url arg						=> FLAG : [928d819fc19405ae09921a2b71227bd9aba106f9d2d37ac412e9e5a750f1506d]





[IDEA] Quand on click sur le logo Born to Sec, une page s'ouvre avec comme url : http://192.168.9.128/?page=e43ad1fdc54babe674da7c7b8f0127bde61de3fbe01def7d00f151c2fcca6d1c l'id ressemble beaucoup a un flag mais je suis pas sur 

[IDEA] :

	- 1 union select table_schema,table_name from information_schema.tables, on voit une db MEMBER_BRUT_FORCE contenant une table db_default

	- 1 union select null,group_concat(column_name) from information_schema.columns where table_name = 0x64625f64656661756c74, il y a id,username,password

	- 1 union select title,comment from Member_Brut_Force.db_default

	- SELECT command denied to user borntosec@localhost for table 'db_default




	grantee : 'borntosec'@'localhost'
	privilege_type : USAGE
	is_grantable : NO