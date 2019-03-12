# บล็อคเชน
แหล่งความรู้บล็อคเชน สำหรับตั้งแต่คนที่ไม่รู้จัก ไปจนถึงคนที่ต้องการเขียนเหรียญตัวเอง

สารบัญ:

ความรู้พื้นฐาน(non technical)

- [บล็อคเชนคืออะไร?](#บล็อคเชนคืออะไร?)
    - [ฐานข้อมูลกระจาย(Distributed Ledger)](#ฐานข้อมูลกระจายdistributed-ledger)
    - [ข้อตกลงร่วมในระบบ(Consensus Mechanism)](#ข้อตกลงร่วมในระบบConsensus-Mechanism)
    - [การขุดเหมืองบล็อคเชน(Mining)](#การขุดเหมืองบล็อคเชน)
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

- [อีเธอเรียมคืออะไร?](#อีเธอเรียมคืออะไร?)
    - [บัญชีบนบล็อคเชน(accounts)](#บัญชีบนบล็อคเชน)
    - [การเชื่อมต่อข้อมูลบนบล็อคเชน(transactions)](#การเชื่อมต่อข้อมูลบนบล็อคเชน`(transactions`))
    - [ค่าธรรมเนียมแก๊ส](#ค่าธรรมเนียมแก๊ส)
    - [โครงสร้างอีเธอเรียม](#โครงสร้างอีเธอเรียม)
- [สมาร์ทคอนแทรค](#สมาร์ทคอนแทรค)
    - [แอพต่างๆที่ใช้เขียนสมาร์ทคอนแทรค](#แอพต่างๆที่ใช้เขียนสมาร์ทคอนแทรค)
    - [ขั้นตอนการเขียนสมาร์ทคอนแทรค](#ขั้นตอนการเขียนสมาร์ทคอนแทรค)
    
การเขียนแอพบนบล็อคเชนอีเธอเรียม(technical)

- [บล็อคเชนทำงานอย่างไร?](#บล็อคเชนทำงานอย่างไร?)
    - [การเข้ารหัสแฮช](#การเข้ารหัสแฮช)
    - [การอนุญาตและสิทธิ์ในการเข้าถึงข้อมูล(public key)](#การอนุญาตและสิทธิ์ในการเข้าถึงข้อมูล`(public-key`))
    - [เมอร์เคิลทรี(Merkle trees)](#เมอร์เคิลทรี`(Merkle-trees`))
    - [โครงสร้างของบล็อคเชน](#โครงสร้างของบล็อคเชน)
    - [ฐานข้อมูลบล็อคเชน(nodes)](#ฐานข้อมูลบล็อคเชน`(nodes`))
    - [การแก้ไขระบบบล็อคเชน(fork)](#การแก้ไขระบบบล็อคเชน`(fork`))
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

### ฐานข้อมูลกระจาย(Distributed Ledger)
บล็อคเชนถือเป็น [Distributed Ledger](https://www.investopedia.com/terms/d/distributed-ledgers.asp) รูปแบบหนึ่ง ฐานข้อมูลประเภทนี้จะเก็บข้อมูลชุดเดียวกันไว้หลายๆฐานเพื่อใช้เปรียบเทียบกัน

### ข้อตกลงร่วมในระบบ(Consensus Mechanism)
[Consensus Mechanism](https://www.investopedia.com/terms/c/consensus-mechanism-cryptocurrency.asp) คือข้อตกลงที่ใช้ร่วมกันระหว่าง node ในการทำให้ข้อมูลทั้งหมดเป็นชุดเดียวกัน

### Solidity
เรียนรู้การเขียน Solidity ฟรีผ่านเกม [cryptozombies](https://cryptozombies.io/)

### Infura
ปกติการจะ deploy smart contracts เราจะต้องเปิด node ตัวเองเพื่อเข้าร่วมระบบ [Infura](https://infura.io/) ช่วยทำหน้าที่ตรงนี้ให้
