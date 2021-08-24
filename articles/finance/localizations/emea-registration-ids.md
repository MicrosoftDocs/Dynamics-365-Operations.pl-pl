---
title: Identyfikatory rejestracji
description: Ten temat zawiera informacje o konfigurowaniu i używaniu identyfikatorów rejestracyjnych.
author: ShylaThompson
ms.date: 11/08/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirPartTaxRegistrationSearch, LogisticsPostalAddress, TaxRegistrationLegislationTypes, TaxRegistrationType
audience: Application User
ms.reviewer: kfend
ms.custom: 264824
ms.search.region: Global
ms.author: vlru
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 544e994a18811995afc64c052a3f97e622529162b8a14b17206c370026b78ac4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6782823"
---
# <a name="registration-ids"></a>Identyfikatory rejestracji

[!include [banner](../includes/banner.md)]

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
| Kategoria rejestracji | Unikatowy identyfikator rejestracyjny dopuszczony do używania w kraju. Pełna lista obsługiwanych kategorii znajduje się w dalszej części tego tematu. |

## <a name="enter-registration-ids-for-global-address-book-records"></a>Wprowadzanie identyfikatorów rejestracyjnych dla rekordów globalnej książki adresowej

Globalna książka adresowa (GAB) zawiera skonsolidowane informacje adresowe odbiorców, dostawców, osób kontaktowych, podmiotów w relacjach biznesowych i firm. Aby uzyskać więcej informacji, zobacz [Omówienie globalnej książki adresowej](../../fin-ops-core/fin-ops/organization-administration/overview-global-address-book.md). Rekordy stron przechowywane w globalnej książce adresowej mogą zawierać jeden lub więcej rekordów adresów. Adresy te są używane do różnych celów, takich jak płatności lub dostawy. Można konfigurować identyfikatory rejestracyjne do informacji adresowych dla odbiorców, dostawców, pracowników i firm. Odszukaj rekord strony (firmy, dostawcy, odbiorcy, pracownika), dla której chcesz wprowadzić identyfikator rejestracji, a następnie w formularzu strony (firmy, dostawcy, odbiorcy, pracownika) kliknij przycisk **Identyfikatory rejestracji**, a zostanie otwarta strona **Zarządzanie adresami**. Na karcie **Rejestracja podatkowa** kliknij przycisk **Dodaj** i wprowadź następujące informacje dotyczące identyfikatora rejestracyjnego.


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
W poniższej tabeli wymieniono obsługiwane typy rejestracji. Dla użytkowników zaznajomionych z polami rozwiązania Microsoft Dynamics AX 2012 dotyczącymi identyfikatorów rejestracyjnych tabela mapuje również te pola na kategorie rejestracji w Dynamics 365 Finance.

| Kategoria rejestracji w programie Finance         |Kraj/region  | Termin/pole w systemie Dynamics AX 2012|
|---------------------------------------------------------------|---------------------|---------------------------------|
| Identyfikator VAT                                                        | Wszystkie kraje Unii Europejskiej (UE)|  Numer identyfikacji podatkowej (typ ustawodawczy Identyfikator podatku w systemie AX 2012 R3)|
| Identyfikator przedsiębiorstwa (COID)                                          | Belgia Czechy Estonia Węgry Łotwa Litwa Polska Szwajcaria | Numer przedsiębiorstwa (EnterpriseNumber) NIP (RegNum\_W) NIP (RegNum\_W) NIP (RegNum\_W) NIP (RegNum\_W) Kod przedsiębiorstwa (EnterpriseCode) NIP (RegNum\_W) UID (typ ustawodawczy UID w systemie AX 2012 R3) |
| Identyfikator oddziału                                                     | Belgia            | Numer partii (BranchNumber)|
| Spisová značka (NIP, Agencja wystawiająca, Sekcja) | Czechy     | Numer wpisu (CommercialRegisterInsetNumber) Przechowywane w rejestrze handlowym (CommercialRegister) Sekcja rejestru handlowego (CommercialRegisterSection)|
| Identyfikator odbiorcy cła                                           | Finlandia | Cło — numer odbiorcy (CustomsCustomerNumber\_FI)|
| Numer identyfikacyjny                                                           | Federacja Rosyjska| Numer identyfikacyjny (typ ustawodawczy Numer identyfikacyjny w systemie AX 2012 R3)|
| Kod przyczyny rejestracji                                                           | Federacja Rosyjska| Numer identyfikacyjny (typ ustawodawczy Numer identyfikacyjny w systemie AX 2012 R3)|
| Klasyfikacja OKDP                                                          | Federacja Rosyjska| Numer identyfikacyjny (typ ustawodawczy Numer identyfikacyjny w systemie AX 2012 R3)|
| Klasyfikacja OKPO                                                          | Federacja Rosyjska| Numer identyfikacyjny (typ ustawodawczy Numer identyfikacyjny w systemie AX 2012 R3)|
| Klasyfikacja RCOAD                                                         | Federacja Rosyjska| Klasyfikacja RCOAD (typ ustawodawczy Klasyfikacja RCOAD w systemie AX 2012 R3)|
| Numer OGRN                                                          | Federacja Rosyjska| Numer identyfikacyjny (typ ustawodawczy Numer identyfikacyjny w systemie AX 2012 R3) |
| Numer SNILS                                                         | Federacja Rosyjska| Numer SNILS (typ ustawodawczy Numer SNILS w systemie AX 2012 R3)|
| Numer CIFTS                                                         | Federacja Rosyjska| Numer CIFTS (typ ustawodawczy CIFTS w systemie AX 2012 R3)|
| Paszport                                                      | Hiszpania             | Paszport|
| Oficjalny dokument tożsamości                              | Hiszpania             | Oficjalny dokument tożsamości|
| Certyfikat rezydencji                                         | Hiszpania             | Certyfikat rezydencji|
| Inny dokument tożsamości                                 | Hiszpania             | Inny dokument tożsamości|
| Nie zliczono                                                  | Hiszpania             | Niedostępne w systemie AX 2012 R3|


Aby uzyskać więcej informacji na temat przetwarzania identyfikatorów rejestracyjnych, w tym opis wymagań wstępnych, zobacz następujące nagrania zadań o identyfikatorach podatkowych w usłudze Lifecycle Services (LCS):

-   Konfigurowanie identyfikatora VAT
-   Rejestrowanie identyfikatora VAT dostawcy
-    Szukanie strony za pomocą identyfikatora VAT






[!INCLUDE[footer-include](../../includes/footer-banner.md)]