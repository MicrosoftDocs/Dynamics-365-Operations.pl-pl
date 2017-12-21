---
title: Identyfikatory rejestracji
description: "Ten temat zawiera informacje o konfigurowaniu i używaniu identyfikatorów rejestracyjnych."
author: ShylaThompson
manager: AnnBe
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DirPartTaxRegistrationSearch, LogisticsPostalAddress, TaxRegistrationLegislationTypes, TaxRegistrationType
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 264824
ms.search.region: Global
ms.author: vlru
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 3d3ad89f80c3e3f42e117109f4a76232795b7d64
ms.openlocfilehash: e908d4ec41263ed4230ea5e70fa08db793abedc6
ms.contentlocale: pl-pl
ms.lasthandoff: 11/28/2017

---

# <a name="registration-ids"></a>Identyfikatory rejestracji

[!include[banner](../includes/banner.md)]


Ten temat zawiera informacje o konfigurowaniu i używaniu identyfikatorów rejestracyjnych.

Wiele krajów i regionów ma róże przepisy i wymagania dotyczące przechowywania numerów lub identyfikatorów rejestracyjnych. Ten temat zawiera omówienie wymaganych ustawień i przetwarzania obsługiwanych typów rejestracji dla podmiotów w różnych krajach/regionach Europy. Wszystkie kraje/regiony mają swoje wymagania dotyczące obsługi różnych funkcji specyficznych dla kraju związanych z numerami rejestracyjnymi nadawanymi przez różne krajowe urzędy. Przykładami numerów rejestracyjnych są numer w powszechnym elektronicznym systemie ewidencji ludności (PESEL), numer identyfikacji podatkowej (NIP) i europejski numer płatnika VAT (europejski identyfikator VAT). Ta funkcja oferuje jednolite środowisko dla wszystkich krajów we wszystkich regionach, uwzględniając specyficzne wymogi niektórych państw europejskich. W poniższych sekcjach opisano cały przepływ informacji używanych do konfigurowania i przetwarzania identyfikatorów rejestracyjnych.

## <a name="registration-type-creation"></a>Tworzenie typu rejestracji
Przed wprowadzeniem identyfikatora rejestracyjnego należy zdefiniować typy rejestracji dla różnych rodzajów numerów rejestracyjnych używanych przez podmioty. Przejdź do strony **Administrowanie organizacją** &gt; **Globalna książka adresowa** &gt; **Typy rejestracji** &gt; **Typy rejestracji**, na której można tworzyć i obsługiwać typy rejestracji dla dostawców, odbiorców, pracowników i firm w różnych krajach/regionach.

|Pole                 |opis      |
|------------------------------|----------------------------|                                                                           
| Nazwisko                | Nazwa typu rejestracji. |                                                                           
| opis         | Opis typu rejestracji. |
| Kraj/region      | Unikatowy identyfikator kraju/regionu.|
| Urząd skarbowy       | Urząd skarbowy skojarzony z typem rejestracji.|
| Ograniczone do       | Rodzaj ograniczenia mający zastosowanie do typu rejestracji podatkowej: Brak, Osoba, Organizacja.|
| Format              | Format weryfikacji typu rejestracji.|
| Możliwa aktualizacja      | Określa, czy numer rejestracyjny w danym typie rejestracji może być aktualizowany po wprowadzeniu.|
| Unikatowa              | Określa, czy numer rejestracyjny w danym typie rejestracji jest unikatowy. |
| Podstawowy dla kraju | Jeśli podmiot jest skojarzony z jednym lub więcej adresami w określonym kraju, a identyfikator rejestracyjny jest prawidłowy dla wszystkich tych adresów, należy wyznaczyć jeden adres jako podstawowy dla kraju. Tylko jeden identyfikator można zarejestrować jako podstawowy. Określa, czy numer rejestracyjny można wprowadzić tylko dla podstawowego adresu kraju. |

## <a name="assign-a-registration-type-to-a-registration-category"></a>Przypisywanie typu rejestracji do kategorii rejestracji
Kategoria rejestracji to identyfikator rejestracyjny kraju/regionu zatwierdzony do używania w określonym kraju/regionie do celów podatkowych, celnych i innych. Ta kategoria definiuje reguły sprawdzania poprawności określonego identyfikatora rejestracyjnego (w tym cyfry kontrolne itp.) i umieszczania identyfikatora rejestracyjnego w różnych raportach. Na stronie **Administrowanie organizacją** &gt; **Globalna książka adresowa** &gt; **Typy rejestracji** &gt; **Kategorie rejestracji** można przypisać typ rejestracji danego kraju do obsługiwanej rejestracji kategorii.

| Pole            | opis|
|-----------------------|----------------|
| Typ rejestracji     | Typ rejestracji w określonym kraju/regionie.|
| Ograniczone do         | Rodzaj ograniczenia stosowany do typu rejestracji podatkowej: Brak, Osoba, Organizacja.|
| Kategoria rejestracji | Unikatowy identyfikator rejestracyjny dopuszczony do używania w kraju. Poniżej znajduje się kompletna lista kategorii obsługiwanych w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. |

## <a name="enter-registration-ids-for-global-address-book-records"></a>Wprowadzanie identyfikatorów rejestracyjnych dla rekordów globalnej książki adresowej

Globalna książka adresowa (GAB) w programie Microsoft Finance and Operations zawiera skonsolidowane informacje adresowe odbiorców, dostawców, osób kontaktowych, podmiotów w relacjach biznesowych i firm. Aby uzyskać więcej informacji, zobacz [Omówienie globalnej książki adresowej](../../fin-and-ops/organization-administration/overview-global-address-book.md). Rekordy stron przechowywane w globalnej książce adresowej mogą zawierać jeden lub więcej rekordów adresów. Adresy te są używane do różnych celów, takich jak płatności lub dostawy. Można konfigurować identyfikatory rejestracyjne do informacji adresowych dla odbiorców, dostawców, pracowników i firm. Odszukaj rekord strony (firmy, dostawcy, odbiorcy, pracownika), dla której chcesz wprowadzić identyfikator rejestracji, a następnie w formularzu strony (firmy, dostawcy, odbiorcy, pracownika) kliknij przycisk **Identyfikatory rejestracji**, a zostanie otwarta strona **Zarządzanie adresami**. Na karcie **Rejestracja podatkowa** kliknij przycisk **Dodaj** i wprowadź następujące informacje dotyczące identyfikatora rejestracyjnego.


|Pole                |opis                                                |
|---------------------|-----------------------------------------------------------|
| Typ rejestracji   | Typ rejestracji w wybranym kraju/regionie.     |
| NIP | Identyfikatora rejestracyjny firmy.                                |
| opis         | Opis numeru rejestracyjnego.               |
| Sekcja             | Dodatkowe informacje o numerze rejestracyjnym. |
| Agencja wystawiająca      | Urząd, który nadał numer rejestracyjny.        |
| Data wystawienia         | Data nadania numeru rejestracyjnego.              |
| Weszła w życie           | Data rozpoczęcia obowiązywania numeru rejestracyjnego.           |
| Data wygaśnięcia          | Data ważności numeru identyfikacyjnego.          |

> [!NOTE]
> Numer identyfikacji podatkowej firmy, dostawcy lub odbiorcy można wybrać spośród identyfikatorów rejestracyjnych powiązanych z identyfikatorem VAT i wprowadzonych dla strony (podmiotu).

## <a name="search-for-records-by-registration-id"></a>Wyszukiwanie rekordów według identyfikatora rejestracyjnego
Funkcja wyszukiwania rekordów stron na podstawie identyfikatorów rejestracyjnych jest dostępna w formularzach strony, firmy, dostawcy, odbiorcy i pracownika. Kliknij przycisk **Wyszukiwanie identyfikatorów rejestracji**, a zostanie otwarta strona **Kryteria wyszukiwania identyfikatorów rejestracji**. Określ kryteria wyszukiwania i kliknij przycisk **Znajdź**. System wyświetli wybrane rekordy z globalnej książki adresowej oraz odnośne typy rekordów stron.

## <a name="supported-registration-categories"></a>Obsługiwane kategorie rejestracji
Poniższa tabela zawiera listę typów rejestracji obsługiwanych w usłudze Finance and Operations. Dla użytkowników zaznajomionych z polami systemu Microsoft Dynamics AX 2012 dotyczącymi identyfikatorów rejestracyjnych tabela mapuje również te pola na kategorie rejestracji w programie Finance and Operations.

| Kategoria rejestracji w programie Finance and Operations         |Kraj/region  | Termin/pole w systemie Dynamics AX 2012|
|---------------------------------------------------------------|---------------------|---------------------------------|
| Identyfikator VAT                                                        | Wszystkie kraje Unii Europejskiej (UE)|  Numer identyfikacji podatkowej (typ ustawodawczy Identyfikator podatku w systemie AX 2012 R3)|
| Identyfikator przedsiębiorstwa (COID)                                          | Belgia Czechy Estonia Węgry Łotwa Litwa Polska Szwajcaria | Numer przedsiębiorstwa (EnterpriseNumber) NIP (RegNum\_W) NIP (RegNum\_W) NIP (RegNum\_W) NIP (RegNum\_W) Kod przedsiębiorstwa (EnterpriseCode) NIP (RegNum\_W) UID (typ ustawodawczy UID w systemie AX 2012 R3) |
| Identyfikator oddziału                                                     | Belgia            | Numer partii (BranchNumber)|
| Spisová značka (NIP, Agencja wystawiająca, Sekcja) | Czechy     | Numer wpisu (CommercialRegisterInsetNumber) Przechowywane w rejestrze handlowym (CommercialRegister) Sekcja rejestru handlowego (CommercialRegisterSection)|
| Identyfikator odbiorcy cła                                           | Finlandia | Cło — numer odbiorcy (CustomsCustomerNumber\_FI)|
| Numer identyfikacyjny                                                           | Federacja Rosyjska| Numer identyfikacyjny (typ ustawodawczy Numer identyfikacyjny w systemie AX 2012 R3)|
| Kod przyczyny rejestracji                                                           | Federacja Rosyjska| Kod przyczyny rejestracji (typ ustawodawczy Kod przyczyny rejestracji w systemie AX 2012 R3)|
| Klasyfikacja OKDP                                                          | Federacja Rosyjska| Klasyfikacja OKDP (typ ustawodawczy Klasyfikacja OKDP w systemie AX 2012 R3)|
| Klasyfikacja OKPO                                                          | Federacja Rosyjska| Klasyfikacja OKPO (typ ustawodawczy Klasyfikacja OKPO w systemie AX 2012 R3)|
| Klasyfikacja RCOAD                                                         | Federacja Rosyjska| Klasyfikacja RCOAD (typ ustawodawczy Klasyfikacja RCOAD w systemie AX 2012 R3)|
| Numer OGRN                                                          | Federacja Rosyjska| Numer OGRN (typ ustawodawczy Numer OGRN w systemie AX 2012 R3) |
| Numer SNILS                                                         | Federacja Rosyjska| Numer SNILS (typ ustawodawczy Numer SNILS w systemie AX 2012 R3)|
| Numer CIFTS                                                         | Federacja Rosyjska| Numer CIFTS (typ ustawodawczy Numer CIFTS w systemie AX 2012 R3)|
| Paszport                                                      | Hiszpania             | Paszport|
| Oficjalny dokument tożsamości                              | Hiszpania             | Oficjalny dokument tożsamości|
| Certyfikat rezydencji                                         | Hiszpania             | Certyfikat rezydencji|
| Inny dokument tożsamości                                 | Hiszpania             | Inny dokument tożsamości|
| Niezliczone                                                  | Hiszpania             | Niedostępne w systemie AX 2012 R3|


Aby uzyskać więcej informacji na temat przetwarzania identyfikatorów rejestracyjnych, w tym opis wymagań wstępnych, zobacz następujące nagrania zadań o identyfikatorach podatkowych w usłudze Lifecycle Services (LCS):

-   Konfigurowanie identyfikatora VAT
-   Rejestrowanie identyfikatora VAT dostawcy
-    Szukanie strony za pomocą identyfikatora VAT





