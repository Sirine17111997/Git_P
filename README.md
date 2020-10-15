ToCode2
XML Exercises
Exercice 1
Création d’un livre en XML
<?xml version="1.0" encoding="iso-8859-1"?>
<livre>
<titre>Mon livre</titre>
<auteurs>
<auteur><nom> ahmed</nom><prenom>mohamed</prenom></auteur>
<auteur><nom>sabbeh</nom><prenom>sirine</prenom></auteur>
</auteurs>
<sections>
<section>
<titre>Section 1</titre>
<chapitres>
<chapitre>
<titre>Chapitre 1</titre>
<paragraphes>
<paragraphe>Premier paragraphe</paragraphe>
<paragraphe>Deuxième paragraphe</paragraphe>
</paragraphes>
</chapitre>
<chapitre>
<titre>Chapitre 2</titre>
<paragraphes>
<paragraphe>Premier paragraphe</paragraphe>
<paragraphe>Deuxième paragraphe</paragraphe>
</paragraphes>
</chapitre>
</chapitres>
</section>
<section>
<titre>Section 2</titre>
<chapitres>
<chapitre>
<titre>Chapitre 1</titre>
<paragraphes>
<paragraphe>Premier paragraphe</paragraphe>
<paragraphe>Deuxième paragraphe</paragraphe>
</paragraphes>
</chapitre>
<chapitre>
<titre>Chapitre 2</titre>
<paragraphes>
<paragraphe>Premier paragraphe</paragraphe>
<paragraphe>Deuxième paragraphe</paragraphe>
</paragraphes>
</chapitre>
</chapitres>
</section>
</sections>
</livre>


Exercice 2
Utilisation des attributs
<?xml version="1.0" encoding="iso-8859-1"?>
<livre titre="Mon livre">
<auteurs>
<auteur nom=" ahmed " prenom="mohamed"/>
<auteur nom="sabbeh" prenom="sirine"/>
</auteurs>
<sections>
<section titre="Section 1">
<chapitre titre="Chapitre 1">
<paragraphe>Premier paragraphe</paragraphe>
<paragraphe>Deuxième paragraphe</paragraphe>
</chapitre>
<chapitre titre="Chapitre 2">
<paragraphe>Premier paragraphe</paragraphe>
<paragraphe>Deuxième paragraphe</paragraphe>
</chapitre>
</section>
<section titre="Section 2">
<chapitre titre="Chapitre1">
<paragraphe>Premier paragraphe</paragraphe>
<paragraphe>Deuxième paragraphe</paragraphe>
</chapitre>
<chapitre titre="Chapitre 2">
<paragraphe>Premier paragraphe</paragraphe>
<paragraphe>Deuxième paragraphe</paragraphe>
</chapitre>
</section>
</sections>
</livre>


Exercice 3
Utilisation des entités prédéfinies
<?xml version="1.0" encoding="iso-8859-1"?>
<livre titre="Mon livre">
<auteurs>
<auteur nom="ahmed" prenom="mohamed"/>
<auteur nom="sabbeh" prenom="sirine"/>
</auteurs>
<sections>
<section titre="Section 1">
<chapitre titre="Chapitre 1">
<paragraphe>Premier paragraphe</paragraphe>
<paragraphe>Deuxième paragraphe</paragraphe>
</chapitre>
<chapitre titre="Chapitre 2">
<paragraphe>Premier paragraphe</paragraphe>
<paragraphe>Deuxième paragraphe</paragraphe>
</chapitre>
</section>
<section titre="Section 2">
<chapitre titre="Chapitre1">
<paragraphe>&lt;element id="10"&gt;&amp;gt;&lt;/element&gt;</paragraphe>
<paragraphe><![CDATA[<element id="10">&gt;</element>]]></paragraphe>
</chapitre>
<chapitre titre="Chapitre 2">
<paragraphe>Premier paragraphe</paragraphe>
<paragraphe>Deuxième paragraphe</paragraphe>
</chapitre>
</section>
</sections>
</livre>

Exercice 4
Utilisation des espaces de noms par défaut et avec préfixe
<p1:livre titre="Mon livre" xmlns:p1="http://www.masociete.com"
➥xmlns:p2="http://www.monentreprise.com">
<p1:auteurs>
<p1:auteur nom="nom1" prenom="prenom1"/>
<p1:auteur nom="nom2" prenom="prenom2"/>
</p1:auteurs>
<p1:sections>
<p1:section titre="Section1">
<p1:chapitre titre="Chapitre1">
<p1:paragraphe>Premier paragraphe</p1:paragraphe>
<p1:paragraphe>Deuxième paragraphe</p1:paragraphe>
</p1:chapitre>
</p1:section>
<p2:section titre="Section2">
<p2:chapitre titre="Chapitre1">
<p2:paragraphe>Premier paragraphe</p2:paragraphe>
<p2:paragraphe>Deuxième paragraphe</p2:paragraphe>
</p2:chapitre>
<p2:chapitre titre="Chapitre2">
<p2:paragraphe>Premier paragraphe</p2:paragraphe>
<paragraphe>Deuxième paragraphe</paragraphe>
</p2:chapitre>
</p2:section>
</p1:sections>
</p1:livre>



Exercice 5
Validation d’un document XML par rapport à un schéma.
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
<!-- Define the elements that make up a Member's Name -->
<!-- Define a Member -->
<xs:element name="Member">
<xs:complexType>
<xs:sequence>
<xs:element name="Name" type="NameType" />
<xs:element name="email" type="xs:string" minOccurs="0" />
</xs:sequence>
<xs:attribute name="id" type="xs:ID" use="required" />
<xs:attribute name="clubs" type="xs:IDREFS" use="optional" />
</xs:complexType>
</xs:element>
<!-- Define the Club root element -->
<xs:element name="Club">
<xs:complexType>
<xs:sequence>
<xs:element ref="Member" />
</xs:sequence>
<xs:attribute name="clubId" type="xs:ID" use="required" />
</xs:complexType>
</xs:element>
<xs:complexType name="NameType" >
<xs:sequence>
<xs:element name="FirstName" type="xs:string" />
<xs:element name="MiddleInitial" type="xs:string"  minOccurs="0"/>
<xs:element name="LastName" type="xs:string" />
</xs:sequence>
</xs:complexType>
</xs:schema>
Exercice 6.
Réalisation d’un schéma

<?xml version="1.0" encoding="ISO-8859-1"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
<xs:complexType name="numerosType">
<xs:sequence>
<xs:element name="contact" type="contactType" maxOccurs="unbounded"/>
</xs:sequence>
</xs:complexType>
<xs:complexType name="contactType">
<xs:sequence>
<xs:element name="nom" type="xs:string"/>
<xs:element name="prenom" type="xs:string"/>
<xs:element name="telephone" type="xs:string" minOccurs="0"/>
<xs:element name="email" type="xs:string" maxOccurs="unbounded"/></xs:sequence>
<xs:attribute name="titre" type="xs:string" use="required"/>
<xs:attribute name="techno" type="xs:string" use="optional"/>
</xs:complexType>
<xs:element name="numeros" type="numerosType"/>
</xs:schema>

Exercice 7.
Construction de types simples

<?xml version="1.0" encoding="ISO-8859-1"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
<xs:simpleType name="technoType">
<xs:restriction base="xs:string">
<xs:enumeration value="XML"/>
<xs:enumeration value="Java"/>
<xs:enumeration value="Autre"/>
</xs:restriction>
</xs:simpleType>
<xs:simpleType name="listIntType">
<xs:list itemType="xs:int">
</xs:list>
</xs:simpleType>
<xs:simpleType name="telType">
<xs:restriction base="listIntType">
<xs:length value="5"/>
</xs:restriction>
</xs:simpleType>
<xs:complexType name="numerosType">
<xs:sequence>
<xs:element name="contact" type="contactType" maxOccurs="unbounded"/>
</xs:sequence>
</xs:complexType>
<xs:complexType name="contactType">
<xs:sequence>
<xs:element name="nom" type="xs:string"/>
<xs:element name="prenom" type="xs:string"/>
<xs:element name="telephone" type="xs:string" minOccurs="0"/>
<xs:element name="email" type="xs:string" maxOccurs="unbounded"/></xs:sequence>
<xs:attribute name="titre" type="xs:string" use="required"/>
<xs:attribute name="techno" type="xs:string" use="optional"/>
</xs:complexType>
<xs:element name="numeros" type="numerosType"/>
</xs:schema
