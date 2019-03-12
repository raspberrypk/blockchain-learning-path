# บล็อคเชน
แหล่งความรู้บล็อคเชน สำหรับตั้งแต่คนที่ไม่รู้จัก ไปจนถึงคนที่ต้องการเขียนเหรียญตัวเอง

สารบัญ:

ความรู้พื้นฐาน(non technical)

- [บล็อคเชนคืออะไร?](#บล็อคเชนคืออะไร)
    - [ฐานข้อมูลกระจาย(Distributed Ledgers)](#ฐานข้อมูลกระจายdistributed-ledgers)
    - [ข้อตกลงร่วมในระบบ(Consensus Mechanism)](#ข้อตกลงร่วมในระบบConsensus-Mechanism)
    - [การขุดเหมืองบล็อคเชน(Mining)](#การขุดเหมืองบล็อคเชนmining)
    - [บล็อคเชนสาธารณะและบล็อคเชนส่วนตัว](#บล็อคเชนสาธารณะและบล็อคเชนส่วนตัว)
- [คุณสมบัติบล็อคเชน](#คุณสมบัติบล็อคเชน)
    - [ข้อดีของแอพบล็อคเชน](#ข้อดีของแอพบล็อคเชน)
    - [ความเข้าใจผิดเกี่ยวกับบล็อคเชน](#ความเข้าใจผิดเกี่ยวกับบล็อคเชน)
- [เหรียญคริปโต](#เหรียญคริปโต)
    - [Bitcoin](#Bitcoin)
    - [Ethereum](#Ethereum)
    - [XRP](#XRP)
    - [Litecoin](#Litecoin)
    - [EOS](#EOS)

Ethereum(intermediate)

- [อีเธอเรียมคืออะไร?](#อีเธอเรียมคืออะไร)
    - [บัญชีบนบล็อคเชน(accounts)](#บัญชีบนบล็อคเชนaccounts)
    - [การเชื่อมต่อข้อมูลบนบล็อคเชน(transactions)](#การเชื่อมต่อข้อมูลบนบล็อคเชนtransactions)
    - [ค่าธรรมเนียมแก๊ส](#ค่าธรรมเนียมแก๊ส)
    - [โครงสร้างอีเธอเรียม](#โครงสร้างอีเธอเรียม)
- [สมาร์ทคอนแทรค](#สมาร์ทคอนแทรค)
    - [เครื่องมือต่างๆที่ใช้เขียนสมาร์ทคอนแทรค](#เครื่องมือต่างๆที่ใช้เขียนสมาร์ทคอนแทรค)
    - [ขั้นตอนการเขียนสมาร์ทคอนแทรค](#ขั้นตอนการเขียนสมาร์ทคอนแทรค)
    
การเขียนแอพบนบล็อคเชนอีเธอเรียม(technical)

- [บล็อคเชนทำงานอย่างไร?](#บล็อคเชนทำงานอย่างไร)
    - [การเข้ารหัสแฮช](#การเข้ารหัสแฮช)
    - [การอนุญาตและสิทธิ์ในการเข้าถึงข้อมูล(public key)](#การอนุญาตและสิทธิ์ในการเข้าถึงข้อมูลpublic-key)
    - [เมอร์เคิลทรี(Merkle trees)](#เมอร์เคิลทรีMerkle-tree)
    - [โครงสร้างของบล็อคเชน](#โครงสร้างของบล็อคเชน)
    - [ฐานข้อมูลบล็อคเชน(nodes)](#ฐานข้อมูลบล็อคเชนnodes)
    - [การอัพเดทระบบบล็อคเชน(fork)](#การอัพเดทระบบบล็อคเชนfork)
- [set up environment ในการเขียน smart contracts](#set-up-environment-ในการเขียน-smart-contracts)
    - [สำหรับ mac](#สำหรับ-mac)
    - [สำหรับ windows](#สำหรับ-windows)
    - [สำหรับ linux](#สำหรับ-linux)
    - [Truffle](#Truffle)
    - [Ganache](#Ganache)
    - [MetaMask](#MetaMask)
- [เขียน smart contracts แรกด้วย Truffle 4.0](#เขียน-smart-contracts-แรกด้วย-Truffle-4.0)
    - [Solidity](#Solidity)
    - [การ deploy contract แบบทำเอง](#การ-deploy-contract-แบบทำเอง)
    - [การ deploy contract ด้วย Truffle](#การ-deploy-contract-ด้วย-Truffle)
    - [การจัดการ error](#การจัดการ-error)
    - [block & transactions](#block-&-transactions)
    - [ค่าธรรมเนียมแก๊ส](#ค่าธรรมเนียมแก๊ส)
    - [การส่งอีเธอเรียมถึงกันและกัน](#การส่งอีเธอเรียมถึงกันและกัน)
- [การออกแบบและพัฒนาแอพบล็อคเชน](#การออกแบบและพัฒนาแอพบล็อคเชน)
    - [การเขียน UI ด้วย web3](#การเขียน-UI-ด้วย-web3)
    - [การเรียกใช้ MetaMask](#การเรียกใช้-MetaMask)
    - [การเรียกใช้งาน events](#การเรียกใช้งาน-events)
    - [การยกเลิก contracts](#การยกเลิก-contracts)
    - [Infura](#Infura)
    
## บล็อคเชนคืออะไร?
บล็อคเชนคือฐานข้อมูลสาธารณะ [ภาพรวมของบล็อคเชน](https://www.youtube.com/watch?v=SSo_EIwHSd4)

### ฐานข้อมูลกระจาย(Distributed Ledgers)
บล็อคเชนถือเป็น [Distributed Ledger](https://www.investopedia.com/terms/d/distributed-ledgers.asp) รูปแบบหนึ่ง ฐานข้อมูลประเภทนี้จะเก็บข้อมูลชุดเดียวกันไว้หลายๆฐานเพื่อใช้เปรียบเทียบกัน

### ข้อตกลงร่วมในระบบ(Consensus Mechanism)
[Consensus Mechanism](https://www.investopedia.com/terms/c/consensus-mechanism-cryptocurrency.asp) คือข้อตกลงที่ใช้ร่วมกันระหว่าง node ในการทำให้ข้อมูลทั้งหมดเป็นชุดเดียวกัน

### การขุดเหรียญคริปโต(Mining)
เราเรียกกระบวนการในการเขียนข้อมูลเพิ่มลงบนบล็อคเชนว่า เป็นการต่อบล็อคใหม่ [การขุดเหรียญคริปโต](https://www.investopedia.com/terms/b/bitcoin-mining.asp) คือกระบวนการในการค้นหาผู้มีสิทธิ์เพียงคนเดียวที่จะสามารถเขียนข้อมูลใหม่ 1 บล็อคลงบนบล็อคเชนได้

### บล็อคเชนสาธารณะและบล็อคเชนส่วนตัว
ส่วนมากบล็อคเชนส่วนตัวจะเป็นที่นิยมใช้กันเองระหว่างองค์กรประเภทธนาคารการเงินที่มีการทำธุรกรรมร่วมกัน โดยทั่วไปจะเรียกตามชื่อเทคโนโลยี เช่น Hyper Ledger เป็นต้น จะไม่เรียกว่าบล็อคเชน [นิยาม](https://medium.com/coinmonks/public-vs-private-blockchain-in-a-nutshell-c9fe284fa39f) ในกรณีทั่วไปแล้ว บล็อคเชน จะหมายถึงบล็อคเชนสาธารณะเท่านั้น

## คุณสมบัติบล็อคเชน
[คุณสมบัติที่สำคัญในการนิยามเทคโนโลยีนี้](https://www.quora.com/What-are-the-key-properties-of-the-Bitcoin-blockchain)

### ข้อดีของแอพบล็อคเชน
[จุดเด่น 5 ประการในการเอาบล็อคเชนเข้ามาประยุกต์ใช้ในธุรกิจ](https://www.ibm.com/blogs/blockchain/2018/02/top-five-blockchain-benefits-transforming-your-industry/)

### ความเข้าใจผิดเกี่ยวกับบล็อคเชน
เทคโนโลยีบล็อคเชนยังถือว่าใหม่มาก หลายคนที่ไม่เข้าใจในเทคโนโลยีนี้ทำให้เกิด [ความเข้าใจผิดไปต่างๆมากมาย](https://www.itproportal.com/features/breaking-down-blockchain-10-common-misconceptions/) เช่น บล็อคเชนเป็นภาพลวงตา เป็นแหล่งฟอกเงิน เป็นแชร์ลูกโซ่หลอกลวง

## เหรียญคริปโต
เราสามารถติดตามศึกษาข้อมูลเหรียญคริปโตทุกเหรียญบนโลกได้จากเว็บ [coinmarketcap](https://coinmarketcap.com/) โดยเว็บเรียงลำดับสกุลเงินให้ตามมูลค่าปัจจุบัน

### Bitcoin
เหรียญคริปโตเหรียญแรกที่ใช้ได้จริง มีมูลค่าสูงที่สุดในตระกูลเหรียญคริปโต [Bitcoin](https://www.youtube.com/watch?v=Gc2en3nHxA4)

### Ethereum
อีเธอเรียมเป็นบล็อคเชนที่สามารถเขียนแอพลงไปได้ [Ethereum](https://www.ethereum.org/)

### XRP
XRP เป็นเหรียญที่เน้นการโอนเงินระหว่างธนาคารข้ามประเทศ เน้นความเสถียรในการใช้งาน [XRP](https://ripple.com/xrp/)

### Litecoin
ไลท์คอยเป็นเหรียญที่ต่อยอดไอเดียระบบมาจากบิทคอยโดยใช้ algorithm ที่ซับซ้อนกว่าแต่เร็วกว่าบิทคอย [Litecoin](https://litecoin.org/)

### EOS
อีออสเป็นบล็อคเชนที่เน้นความเร็วในการเขียนข้อมูลโดยยอมลดระดับความปลอดภัยลง [EOS](https://eos.io/)

## อีเธอเรียมคืออะไร
ปัจจุบัน(มีนาคม 2562)อีเธอเรียมเป็นบล็อคเชนที่มี community ใหญ่ที่สุดในบรรดาบล็อคเชนทุกตระกูล มีนักพัฒนาทั่วโลกช่วยกันคิดผลิตเครื่องมือต่างๆเพื่อผลักดันให้เทคโนโลยีนี้สามารถเข้ามามีบทบาทเปลี่ยนยุคสมัยของคนทุกคนบนโลกในวันข้างหน้า [Ethereum](https://blockgeeks.com/guides/ethereum/)

### บัญชีบนบล็อคเชน(accounts)

### การเชื่อมต่อข้อมูลบนบล็อคเชน(transactions)

### ค่าธรรมเนียมแก๊ส

### โครงสร้างอีเธอเรียม

## สมาร์ทคอนแทรค

### เครื่องมือต่างๆที่ใช้เขียนสมาร์ทคอนแทรค

### ขั้นตอนการเขียนสมาร์ทคอนแทรค

## บล็อคเชนทำงานอย่างไร?

### การเข้ารหัสแฮช

### การอนุญาตและสิทธิ์ในการเข้าถึงข้อมูล(public key)

### เมอร์เคิลทรี(Merkle tree)

### โครงสร้างของบล็อคเชน

### ฐานข้อมูลบล็อคเชน(nodes)

### การอัพเดทระบบบล็อคเชน(fork)

## setting up environment ในการเขียน smart contracts

### สำหรับ Mac

### สำหรับ Windows

### สำหรับ Linux

### Truffle

### Ganache

### MetaMask

## เขียน smart contracts แรกด้วย Truffle 4.0

### Solidity
Solidity เป็นภาษาโปรแกรมมิ่งที่ใช้เขียนสมาร์ทคอนแทรคบนอีเธอเรียมโดยเฉพาะ syntax จะคล้ายกับภาษา JavaScript เรียนรู้การเขียน Solidity ฟรีผ่านเกม [cryptozombies](https://cryptozombies.io/)

### การ deploy contract แบบทำเอง

### การ deploy contract ด้วย Truffle

### การจัดการ error

### block & transactions

### ค่าธรรมเนียมแก๊ส

### การส่งอีเธอเรียมถึงกันและกัน

## การออกแบบและพัฒนาแอพบล็อคเชน

### การเขียน UI ด้วย web3

### การเรียกใช้ MetaMask

### การเรียกใช้งาน events

### การยกเลิก contracts

### Infura
ปกติแล้วการจะ deploy smart contracts ลงอีเธอเรียมนั้นเราจะต้องเปิด node ตัวเองเพื่อเข้าร่วมระบบบล็อคเชน [Infura](https://infura.io/) ช่วยทำหน้าที่ตรงนี้ให้
