---
title: DLP System On Demand
header_icon: /assets/images/icons/icn-documentation.svg
header_title: Qordoba DLP System On Demand
breadcrumbs:
  Security: /security
---


# DLP System On Demand

The DLP API lets you understand and manage sensitive data. It provides fast, scalable classification and optional redaction for sensitive data elements like credit card numbers, names, social security numbers, passport numbers, US and selected international driver’s license numbers, and phone numbers. The API classifies this data using more than 50 predefined detectors to identify patterns, formats, and checksums, and even understands contextual clues. The API supports text and images.



# United States
**Social Security Number**
In the United States, a Social Security number (SSN) is a 9-digit number issued to U.S. citizens, permanent residents, and temporary residents. The Social Security number has become the de facto national identification number for taxation and other purposes.
Detection method: Pattern match or 9 digits with context
Context: SSN, Social, Social Security, Taxpayer
&nbsp;



**Driver's License Number**
Driver's license number for the United States. Format can vary depending on the issuing U.S. state.
Detection method: Pattern match and context
Context: Drive, Driving, Learn, Lic, License, Licence, Permit, DL
Match Quality:: Driver's licenses are not well defined and may generate noise results unless there is clear context.



**Drug Administration Enforcement (DEA) Number**
A DEA number is assigned to a health care provider by the U.S. Drug Enforcement Administration. It allows the health care provider to write prescriptions for controlled substances. The DEA number is often used as a general "prescriber number" that is a unique identifier for anyone who can prescribe medication.
Detection method: Pattern match and checksum



**ABA Routing Number:**The American Bankers Association (ABA) Routing Number (also called the <em>transit number</em>) is a nine-digit code. It's used to identify the financial institution that's responsible to credit or entitled to receive credit for a check or electronic transaction.
Detection method: Checksum on 9 digits
Context: hotwords:
ABA
routing
transit
bank
banking




**National Provider Identifier (NPI):**The National Provider Identifier (NPI) is a unique 10-digit identification number issued to health care providers in the United States by the Centers for Medicare and Medicaid Services (CMS). The NPI has replaced the unique provider identification number (UPIN) as the required identifier for Medicare services. It's also used by other payers, including commercial healthcare insurers.
Detection method: Checksum on 10 digits
&nbsp;




**CUSIP:**A CUSIP number is a 9-character alphanumeric code that identifies a North American financial security.
Detection method: Checksum or context (when check digit not present)
Context: CUSIP




**FDA Approved Prescription Drugs:**This is any drug on the list of prescription drugs approved by the United States Food and Drug Administration (FDA).
Detection method: Word and phrase list




**Passport:**This is a detector for a United States passport.
Detection method: Pattern match and context
Context: United States, USA, Passport, Travel Document



# United Kingdom

**Driver's License Number:**Driver's license number for the United Kingdom of Great Britain and Northern Ireland (UK).
Detection method: Pattern match

**National Health Service (NHS) Number:**NHS numbers are the unique numbers allocated to registered users of the three public health services in England, Wales, and the Isle of Man.
Detection method: Pattern match and checksum
&nbsp;




**National Insurance Number (NINO):**The National Insurance number is a number used in the United Kingdom (UK) in the administration of the National Insurance or social security system. It identifies people. It's also used for some purposes in the UK tax system. The number is sometimes referred to as NI No or NINO.
Detection method: Pattern match (with delimiters) or Pattern match and context words
&nbsp;




**Passport:**This is a detector for a United Kingdom (UK) passport.
Detection method: Pattern match and context
Context: United Kingdom, Passport, Travel Document




**Taxpayer Identification Number:**This is a detector for a United Kingdom (UK) Unique Taxpayer Reference (UTR) number. This number, comprised of a string of 10 decimal digits, is an identifier used by the UK government to manage the taxation system. Unlike other identifiers, such as the passport number or social insurance number, the UTR is not listed on official identity cards.
Detection method: Pattern match and context
Context: United Kingdom, Taxpayer, UTR



# Australia


**Medicare Account Number:**A 9-digit Medicare number is issued to permanent residents of Australia (except for Norfolk island). The primary purpose of this number is to prove Medicare eligibility to receive subsidized care in Australia.
Detection method: Checksum and (pattern match or context)
Context: Medicare, Australia, IRN




**Tax File Number (TFN):**A number issued by the Australian Tax Office for taxpayer identification. Every taxpaying entity, such as an individual or an organization, is assigned a unique number.
Detection method: Checksum and (pattern match or context)
Context: Tax File Number, TFN, Australian Tax Office



# Brazil


**CPF number:**The Cadastro de Pessoas F&iacute;sicas (CPF), which is Portuguese for "Natural Persons Register," is an 11-digit number used in Brazil for taxpayer identification.
Detection method: Checksum and (pattern match or context)
Context: CPF, Cadastro de Pessoas F&iacute;sicas, Pessoas F&iacute;sicas, Tax Number, Taxpayer



# Canada


**Quebec Health Insurance Number (HIN):**The Quebec Health Insurance Number (HIN) is issued to citizens, permanent residents, temporary workers, students and other individuals who are entitled to health care coverage in the Province of Quebec.
Detection method: Pattern match
&nbsp;




**Ontario Health Insurance Plan (OHIP):**The Ontario Health Insurance Plan (OHIP) number is issued to citizens, permanent residents, temporary workers, students, and other individuals who are entitled to health care coverage in the Province of Ontario.
Detection method: Pattern match and checksum
&nbsp;




**British Columbia Personal Health Number (PHN):**The British Columbia Personal Health Number (PHN) is issued to citizens, permanent residents, temporary workers, students, and other individuals who are entitled to health care coverage in the Province of British Columbia.
Detection method: Pattern match or 10 digits with context
Context: BC ID, PHN, British Columbia, Personal Health Number, Services Card, Canadian health insurance number, Canadian health ID
&nbsp;




**Social Insurance Number (SIN):**The Canadian Social Insurance Number (SIN) is the main identifier used in Canada for citizens, permanent residents, and those on work or study visas. With a Canadian SIN and mailing address, one can apply for health care coverage, driver's licenses, and other important services.
Detection method: Checksum and (pattern match or context)
&nbsp;




**Passport:**This is a detector for a Canadian passport.
Detection method: Pattern match and context
Context: Canada, Canadian, Num&eacute;ro de passeport, Passport, Travel Document, document number




# China


**Passport:**This is a detector for a Chinese passport.
Detection method: Pattern match and context
Context: China, Passport, 中华人民共和国护照, 护照号, H&ugrave;zh&agrave;o h&agrave;o, 护照



# France


**National ID Card (CNI):**The Carte Nationale d'Identit&eacute; S&eacute;curis&eacute;e (CNI or CNIS) is the French national identity card. It's an official identity document consisting of a 12-digit ID number. This number is commonly used when opening bank accounts and when paying by check. It can sometimes be used instead of a passport or visa within the European Union (EU) and in some other countries.
Detection method: Pattern match and context
Context: CNI, CNIS (carte nationale d'identit&eacute; securis&eacute;e), identit&eacute;, identite




**Social Security Number (NIR):**The Num&eacute;ro d'Inscription au R&eacute;pertoire (NIR) is a permanent personal ID number that's also known as the French social security number for services including healthcare as well as pensions.
Detection method: Pattern match and checksum




**Passport:**This is a detector for a French passport.
Detection method: Pattern match and context
Context: France, Passport, Passeport, REPUBLIC FRANCAIS, Num&eacute;ro de passeport



# Germany


**Passport:**This is a detector for a German passport. The format of a German passport number is 10 alphanumeric characters, chosen from numerals 0-9 and letters C, F, G, H, J, K, L, M, N, P, R, T, V, W, X, Y, Z.
Detection method: Pattern match and context
Context: GERMANY, REISEPASS, PASSPORT, Europ&auml;ische Union, Bundesrepublik, Deutschland, reisepassnummer



# India


**Personal Permanent Account Number (PAN):**The Personal Permanent Account Number (PAN) is a unique 10-digit alphanumeric identifier used for identification of individuals, particularly those who pay income tax. It's issued by the Indian Income Tax Department. The PAN is valid for the lifetime of the holder.
Detection method: Pattern match and context
Context: India, Account Number, PAN, Taxpayer ID



# Japan


**Passport:**This is a detector for a Japanese passport. The passport number consists of two alphabetic characters followed by seven digits.
Detection method: Pattern match and context
Context: Japan, Passport, パスポート,
パスポート番号




**National ID number:**Sometimes referred to as the 'My Number' This is a relatively new (January 2016) identification number that is analogous to a social security number in the US.
Context:
個人番号
マイナンバー
身分証明書
Individual Number
My Number
Identity Card



# Korea


**Passport:**This is a detector for a Korean passport. There are 2 different formats.
Pre-2008 passport numbers consist of 9 characters. The first 2 characters are the issued local code, corresponding to the holder's gu, or district. The remaining seven digits are the serial number.
Post-2008 passport numbers consist of 9 characters. The first character is either a single letter M, denoting PM passports, or the letter S for PS passports. The remaining 8 digits are the serial number.
Detection method: Pattern match and context
Context: Passport, Korea, 여권, 대한민국




**South Korean Social Security Numbers:**South Korean Social Security Numbers
Detection method: Pattern match, checksum and context
Context: 
korean
korea
KSSN
RRN
resident registration
registration number
social security
주민등록번호
住民登錄番號



# Mexico


**National Identification Number (CURP):**This is a detector for the Mexico Clave &Uacute;nica de Registro de Poblaci&oacute;n (CURP) number. In English, this is the Unique Population Registry Code, or Personal ID Code Number. This is an 18-character state-issued identification number assigned by the Mexican government to citizens or residents of Mexico and used for taxpayer identification.
Detection method: Pattern match and context
Context: CURP, Clave &Uacute;nica, Poblaci&oacute;n, Registro, UPRC, Personal ID, Registry Code




**Passport:**This is a detector for a Mexican passport.
Detection method: Pattern match and context
Context: Mexico, Passport, Pasaporte, M&eacute;xico, Mexican



# Netherlands


**National Identification Number (BSN):**This is a detector for the Netherlands Burgerservicenummer (BSN). It's also known as a Citizen's Service Number. It's a state-issued identification number that's on driver's licenses, passports, and international ID cards.
Detection method: Checksum and (pattern match or context)
Context: BSN, Personal Number, Burgerservicenummer, Netherlands, Identification Number, Service Number, sofinummer, sofi, personalnummer



# Spain


**NIF Number:**N&uacute;mero de Identificaci&oacute;n Fiscal (NIF) numbers are government ID numbers for Spanish citizens. An NIF number is needed for key transactions such as opening a bank account, buying a car, or setting up a mobile phone contract.
Detection method: Checksum and (pattern match or context)
Context: N&uacute;mero de Identificaci&oacute;n Fiscal, NIF
&nbsp;




**NIE Number:**N&uacute;mero de Identificaci&oacute;n de Extranjeros (NIE) numbers are government ID numbers for foreigners living or doing business in Spain. An NIE number is needed for key transactions such as opening a bank account, buying a car, or setting up a mobile phone contract.
Detection method: Checksum and (pattern match or context)
Context: N&uacute;mero de Identificaci&oacute;n de Extranjeros, NIE
&nbsp;




**Passport:**There are 4 different types of passports in Spain. This detector is for the Ordinary Passport (Pasaporte Ordinario) type, which is issued for ordinary travel, such as vacations and business trips.
Detection method: Pattern match and context
Context: Passport, Pasaporte, Espana, Espa&ntilde;a, Spain



# Global


**Credit card number:**Credit card numbers are 12 to 19 digits long. They're used for payment transactions globally.
Detection method: Pattern match and checksum
&nbsp;




**Bank account number (IBAN):**An International Bank Account Number (IBAN) is defined as an internationally agreed-upon method for identifying bank accounts. It's defined by the International Standard of Organization (ISO) 13616:2007 standard. ISO 13616:2007 was created by the European Committee for Banking Standards (ECBS). An IBAN consists of up to 34 alphanumeric characters including elements such as a country code or account number.
Detection method: Pattern match and checksum




**Bank account number (SWIFT):**A SWIFT code is the same as a Bank Identifier Code (BIC). It's a unique identification code for a particular bank. These codes are used when transferring money between banks, particularly for international wire transfers. Banks also use the codes for exchanging other messages.
Detection method: Pattern match and context
Context: SWIFT, ISO 9362, Business Identifier Code, BIC, Business Entity Identifier, BEI, bank, interbank




**ICD 9-CM Lexicon:**The International Classification of Diseases, Clinical Modification (ICD-9-CM) lexicon is used to assign diagnostic and procedure codes associated with inpatient, outpatient, and physician office use in the United States. It was created by the U.S. National Center for Health Statistics (NCHS). The ICD-9-CM is based on the ICD-9 but provides for additional morbidity detail. It's updated annually on October 1.
Detection method: Word and phrase list




**ICD 10-CM Lexicon:**Like ICD 9 codes, ICD 10 codes are a series of diagnostic codes published by the World Health Organization (WHO) to describe causes of morbidity and mortality.
Detection method: Word and phrase list




**International Mobile Equipment Identity:**Detection method: Custom Logic, pattern match and context.
**IP address (IP v4 only):**Detection method: Custom Logic, pattern match and context.
**MAC Address:**Detection method: Custom Logic, pattern match and context
Context: "mac address"
"hardware address"
"physical address"
"hwaddr"
"ether"
"ethernet"
"BSSID"




**Phone Numbers:**Detection method: Custom Logic, pattern match and context



**Email address:**
Email addresses indicate the mailbox that emails are sent to or from. The maximum length of the domain name is 63 characters, and the maximum length of the host name is 253 characters.
Detection method: Pattern and top level domain validation
