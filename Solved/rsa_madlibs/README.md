# rsa-madlibs
Cryptography - 250 points

## Challenge 
> We ran into some weird puzzles we think may mean something, can you help me solve one? 

> Connect with nc 2018shell2.picoctf.com 18148


## Solution

A long challenge covering various questions on RSA calculations

1. Y`p * q = n`
2. `n / p = q`
3. Not possible - not enough info
4. `phi = (p-1) * (q-1)`
5. `c = pow(m, e, n)`
6. Not possible - cuberoot does not yield an integer ([Exploit is when n is very big but e is very small](https://github.com/zst123/gryphonctf-2017-writeups/tree/master/Solved/NoWrap))
7. `d * e == 1 modulo (p-1)(q-1)`
	- [Source](https://stackoverflow.com/questions/16310871/in-rsa-encryption-how-do-i-find-d-given-p-q-e-and-c)
	- [Code](https://gist.github.com/ofaurax/6103869014c246f962ab30a513fb5b49)
8. `m = pow(c, d, n)` and same as 7


Submission

	y
	8815769761
	y
	77773
	n
	y
	6256003596
	y
	26722917505435451150596710555980625220524134812001687080485341361511207096550823814926607028717403343344600191255790864873639087129323153797404989216681535785492257030896045464472300400447688001563694767148451912130180323038978568872458130612657140514751874493071944456290959151981399532582347021031424096175747508579453024891862161356081561032045394147561900547733602483979861042957169820579569242714893461713308057915755735700329990893197650028440038700231719057433874201113850357283873424698585951160069976869223244147124759020366717935504226979456299659682165757462057188430539271285705680101066120475874786208053
	n
	y
	1405046269503207469140791548403639533127416416214210694972085079171787580463776820425965898174272870486015739516125786182821637006600742140682552321645503743280670839819078749092730110549881891271317396450158021688253989767145578723458252769465545504142139663476747479225923933192421405464414574786272963741656223941750084051228611576708609346787101088759062724389874160693008783334605903142528824559223515203978707969795087506678894006628296743079886244349469131831225757926844843554897638786146036869572653204735650843186722732736888918789379054050122205253165705085538743651258400390580971043144644984654914856729
	y
	240109877286251840533272915662757983981706320845661471802585807564915966910385128423526644303028605


## Flag

The flag is the plaintext of question 8

	$ python3 8-getflag.py 
	240109877286251840533272915662757983981706320845661471802585807564915966910385128423526644303028605
	picoCTF{d0_u_kn0w_th3_w@y_2_RS@_b38be18a}