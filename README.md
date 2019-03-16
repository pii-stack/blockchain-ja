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
    - [การเขียน UI ด้วย web3.js](#การเขียน-UI-ด้วย-web3.js)
    - [การเรียกใช้ MetaMask](#การเรียกใช้-MetaMask)
    - [การเรียกใช้งาน events](#การเรียกใช้งาน-events)
    - [การยกเลิก contracts](#การยกเลิก-contracts)
    - [Infura](#Infura)
    
## บล็อคเชนคืออะไร?
บล็อคเชนคือฐานข้อมูลสาธารณะ [คลิปวีดีโออธิบาย Blockchain#1](https://www.youtube.com/watch?v=SSo_EIwHSd4)

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
- [What qualifies as a Blockchain?](https://chainskills.com/2016/11/21/what-qualifies-as-a-blockchain/)

## เหรียญคริปโต
เราสามารถติดตามศึกษาข้อมูลเหรียญคริปโตทุกเหรียญบนโลกได้จากเว็บ [coinmarketcap](https://coinmarketcap.com/) โดยเว็บเรียงลำดับสกุลเงินให้ตามมูลค่าปัจจุบัน

### Bitcoin
เหรียญคริปโตเหรียญแรกที่ใช้ได้จริง มีมูลค่าสูงที่สุดในตระกูลเหรียญคริปโต 
- [คลิปวีดีโออธิบาย Bitcoin](https://www.youtube.com/watch?v=Gc2en3nHxA4)
- [Bitcoin white paper](https://bitcoin.org/bitcoin.pdf)
- [Bitcoin source code](https://github.com/bitcoin/bitcoin)

### Ethereum
อีเธอเรียมเป็นบล็อคเชนที่สามารถเขียนแอพลงไปได้ 
- [Ethereum official website](https://www.ethereum.org/)
- [Ethereum white paper](https://github.com/ethereum/wiki/wiki/White-Paper)
- [Ethereum source code](https://github.com/ethereum/go-ethereum)

### XRP
XRP เป็นเหรียญที่เน้นการโอนเงินระหว่างธนาคารข้ามประเทศ เน้นความเสถียรในการใช้งาน [XRP](https://ripple.com/xrp/)

### Litecoin
ไลท์คอยเป็นเหรียญที่ต่อยอดไอเดียระบบมาจากบิทคอยโดยใช้ algorithm ที่ซับซ้อนกว่าแต่เร็วกว่าบิทคอย [Litecoin](https://litecoin.org/)

### EOS
อีออสเป็นบล็อคเชนที่เน้นความเร็วในการเขียนข้อมูลโดยยอมลดระดับความปลอดภัยลง [EOS](https://eos.io/)

## อีเธอเรียมคืออะไร
ปัจจุบัน(มีนาคม 2562)อีเธอเรียมเป็นบล็อคเชนที่มี community ใหญ่ที่สุดในบรรดาบล็อคเชนทุกตระกูล มีนักพัฒนาทั่วโลกช่วยกันคิดผลิตเครื่องมือต่างๆเพื่อผลักดันให้เทคโนโลยีนี้สามารถเข้ามามีบทบาทเปลี่ยนยุคสมัยของคนทุกคนบนโลกในวันข้างหน้า [บทความอธิบาย Ethereum](https://blockgeeks.com/guides/ethereum/)

### บัญชีบนบล็อคเชน(accounts)
[บัญชีหรือ accounts](https://medium.com/coinmonks/ethereum-account-212feb9c4154) เป็นพื้นฐานการทำงานของระบบอีเธอเรียม

### การเชื่อมต่อข้อมูลบนบล็อคเชน(transactions)
ลักษณะข้อมูลบนอีเธอเรียม [Ethereum transaction](https://thecoinoffering.com/learn/ethereum-transactions/)

### ค่าธรรมเนียมแก๊ส
[ค่าธรรมเนียม](https://kb.myetherwallet.com/gas/what-is-gas-ethereum.html) ในการเขียนข้อมูลลงบนบล็อคเชนคือรายได้ของนักขุดเหมืองเหรียญคริปโตนั่นเอง

### โครงสร้างอีเธอเรียม
อีเธอเรียมเป็นบล็อคเชนสาธารณะ แปลว่าใครก็ได้สามารถเปิด node ขึ้นมาเพื่อรับข้อมูลเชนทั้งหมดมาเก็บไว้ ใครก็ได้สามารถเปิด node มาเพื่อขุดเหรียญ(ต่อบล็อค)อีเธอเรียมตามระเบียบที่วางไว้ได้เช่นกัน [a gentle introduction to Ethereum](https://bitsonblocks.net/2016/10/02/gentle-introduction-ethereum/)

## สมาร์ทคอนแทรค
สมาร์ทคอนแทรคคือข้อตกลงร่วม สัญญาร่วมกันระหว่างแต่ละฝ่าย เงื่อนไขที่ถูกเขียนเป็นกฎลงบนบล็อคเชน [smart contracts simply explained](https://www.youtube.com/watch?v=ZE2HxTmxfrI)

### เครื่องมือต่างๆที่ใช้เขียนสมาร์ทคอนแทรค
Tools และ Frameworks ต่างๆที่ใช้เขียนสมาร์ทคอนแทรค [What are the development tools for Ethereum?](https://ethereum.stackexchange.com/questions/2064/what-are-the-development-tools-for-ethereum)

### ขั้นตอนการเขียนสมาร์ทคอนแทรค
เรียนรู้การเขียนสมาร์ทคอนแทรคจากศูนย์ [Create a Hello World Contract in Ethereum](https://www.ethereum.org/greeter)

## บล็อคเชนทำงานอย่างไร?
บล็อคเชนคือสมุดจดบันทึกที่แก้ไขบรรทัดที่จดไปแล้วไม่ได้
- [คลิปวีดีโออธิบาย Blockchain#2](https://www.youtube.com/watch?v=NTNQMKB0A3A)
- [บล็อคเชนทำงานอย่างไร](https://cointelegraph.com/bitcoin-for-beginners/how-blockchain-technology-works-guide-for-beginners#hash-function)

### การเข้ารหัสแฮช
[การเข้ารหัสแฮช](https://www.youtube.com/watch?v=KyUTuwz_b7Q&t=697s) เป็นวิธีเรียงลำดับข้อมูล(data structure)แบบหนึ่ง แต่ด้วยคุณสมบัติพิเศษของผลลัพธ์แฮช ทำให้มันถูกนำมาใช้ในการ [รักษารหัสผ่าน Password & hash functions](https://www.youtube.com/watch?v=cczlpiiu42M) รวมถึงใช้เทียบข้อมูลระหว่าง node ในบล็อคเชนอีกด้วย

### การอนุญาตและสิทธิ์ในการเข้าถึงข้อมูล(public key)
การรับส่งข้อมูลในที่สาธารณะจำเป็นต้องใช้ [Public and Private Keys](https://www.youtube.com/watch?v=csXb8Qu5NQo) เพื่อความปลอดภัยจากผู้ดักฟัง

### เมอร์เคิลทรี(Merkle tree)
เมอร์เคิลทรีเป็นวิธีการเก็บข้อมูลรูปแบบหนึ่งซึ่งมีคุณสมบัติ[what is Merkle tree](https://blockonomi.com/merkle-tree/)

### โครงสร้างของบล็อคเชน

### ฐานข้อมูลบล็อคเชน(nodes)

### การอัพเดทระบบบล็อคเชน(fork)
โดยทั่วไปแล้วการ fork จะเกิดขึ้นเมื่อนักพัฒนาเห็นตรงกันว่าระบบควรอัพเดทเพื่อให้มีประสิทธิภาพดีขึ้น เมื่อระบบมีการเปลี่ยนแปลง คนขุดเหรียญ(คนต่อบล็อค)ก็จำเป็นต้องแก้ไขระบบตามเพื่อให้ตรงกันกับระบบปัจจุบัน การเปลี่ยนแปลงดังกล่าวทำให้เกิดการแยก(fork)บล็อคออกมาอีกสาย โดยถ้าสายเก่าไม่มีคนใช้ก็จะถูกปล่อยคาทิ้งไว้ตามเดิม [Blockchain Forks Explained](https://medium.com/digitalassetresearch/blockchain-forks-explained-8ccf304b97c8)

## setting up environment ในการเขียน smart contracts

### สำหรับ Mac

### สำหรับ Windows

### สำหรับ Linux

### Truffle
[ทรัฟเฟิล](https://truffleframework.com/) เป็น framework ที่ช่วยเขียนสมาร์ทคอนแทรคที่มีชื่อเสียงมากที่สุด

### Ganache
[กานาช](https://truffleframework.com/ganache) เป็นบล็อคเชนจำลองสำหรับนักพัฒนาไว้ใช้เขียนและทดสอบในเครื่องตัวเอง

### MetaMask
[เมต้ามาสค์](https://metamask.io/) เป็นกระเป๋าตังที่ใช้เก็บอีเธอเรียมได้จริงๆ เป็นอุปกรณ์หนึ่งที่ใช้ในการเขียนแอพบล็อคเชน

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

### การเขียน UI ด้วย web3.js
[web3.js](https://web3js.readthedocs.io/en/1.0/) เป็น framework ที่เชื่อมข้อมูลจากอีเธอเรียมมาเป็น JavaScript

### การเรียกใช้ MetaMask

### การเรียกใช้งาน events

### การยกเลิก contracts

### Infura
ปกติแล้วการจะ deploy smart contracts ลงอีเธอเรียมนั้นเราจะต้องเปิด node ตัวเองเพื่อเข้าร่วมระบบบล็อคเชน [Infura](https://infura.io/) ช่วยทำหน้าที่ตรงนี้ให้
