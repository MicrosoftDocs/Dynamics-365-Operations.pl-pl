---
title: Identyfikatory rejestracji
description: "Ten temat zawiera informacje o konfigurowaniu i używaniu rejestracji identyfikatorów."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DirPartTaxRegistrationSearch, LogisticsPostalAddress, TaxRegistrationLegislationTypes, TaxRegistrationType
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264824
ms.assetid: e86f0a35-be58-4ef5-b5ab-bcfc495eaa13
ms.search.region: Global
ms.author: vlru
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 32cd09975861083b8940368ed53ae16e89bcd748
ms.lasthandoff: 03/31/2017


---

# <a name="registration-ids"></a>Identyfikatory rejestracji

Ten temat zawiera informacje o konfigurowaniu i używaniu rejestracji identyfikatorów.

Wiele krajów i regionów mają różne rozporządzenia i wymagania dotyczące nagrywania numery rejestracyjne lub identyfikatorów. Ten temat zawiera omówienie wymagane ustawienia i przetwarzania typów obsługiwanych rejestracji dla stron w różnych krajach/regionach Europy. Wszystkie kraje/regiony mają swoje wymagania dotyczące obsługi różnych funkcji specyficznych dla kraju związane z numery rejestracyjne dostarczone przez biura w innym stanie. Numery rejestracyjne przykładami, numer PESEL (SSN), numer identyfikacji podatkowej (NIP) i Europejski NIP (numer NIP UE). Ta funkcja zapewnia jednolitych ram dla wszystkich krajów we wszystkich regionach, biorąc pod uwagę specyficzne wymogi niektórych państw europejskich. W poniższych sekcjach opisano ogólny przepływ informacji, który jest używany do konfigurowania i przetwarzanie rejestracji identyfikatorów.

## <a name="registration-type-creation"></a>Tworzenie typu rejestracji
Zanim będzie można wprowadzić identyfikator rejestracji, należy skonfigurować typy rejestracji dla różnych typów numery rejestracyjne, które każda ze stron jest warunkiem. Przejdź do **Administrowanie organizacją**&gt;**globalnej książki adresowej**&gt;**typów rejestracji**&gt;**typów rejestracji** strony do tworzenia i obsługi typów rejestracji dla dostawców, klientów, pracowników i osób prawnych w różnych krajach/regionach.

|Pole                 |opis      |
|------------------------------|----------------------------|                                                                           
| Nazwisko                | Nazwa typu rejestracji. |                                                                           
| opis         | Opis typu rejestracji. |
| Kraj/region      | Identyfikator unikatowy kraju/regionu.|
| Urząd skarbowy       | Urząd skarbowy, który jest skojarzony z typem rejestracji.|
| Ograniczone do       | Rodzaj ograniczenia, które stosuje się do typu identyfikacji podatkowej: Brak, osoba, organizacja.|
| Format              | Format weryfikacji typu identyfikacji.|
| Możliwa aktualizacja      | Określa, czy numer rejestracyjny dla typu rejestracji można aktualizować po jego wprowadzeniu.|
| Unikatowa              | Określa, czy numer rejestracyjny dla typu rejestracji jest unikatowa. |
| Podstawowy dla kraju | Jeśli strona jest skojarzony z jednym lub więcej adresów w szczególności kraj i identyfikator rejestracji jest prawidłowa dla tych adresów, należy wyznaczyć jeden adres jako podstawowy dla kraju. Jeden identyfikator można zarejestrować jedynie jako podstawowy. Określa, czy numer rejestracyjny można wprowadzić tylko dla podstawowego dla adresu kraju. |

## <a name="assign-a-registration-type-to-a-registration-category"></a>Przypisz typ rejestracji do kategorii rejestracji
Kategoria rejestracji jest identyfikator rejestracji kraj/region, dopuszczone do wykorzystania w szczególności kraju/regionu dla podatków, ceł i innych celów. Ta kategoria definiuje reguły sprawdzania poprawności Identyfikatora rejestracji (w tym cyfry kontrolne itp.) i identyfikator rejestracyjny włączenia w różnych raportach. Strona **Administrowanie organizacją**&gt;**globalnej książki adresowej**&gt;**typów rejestracji**&gt;**kategorie rejestracji** Aby przypisać typ rejestracji danego kraju do rejestracji obsługiwanych kategorii.

| Pole            | opis|
|-----------------------|----------------|
| Typ rejestracji     | Rejestracja w szczególności typ kraju/regionu.|
| Ograniczone do         | Rodzaj ograniczeń stosuje się do typu identyfikacji podatkowej: Brak, osoba, organizacja.|
| Kategoria rejestracji | Identyfikator rejestracji unikatowych, dopuszczone do wykorzystania w kraju. Pełna lista obsługiwanych w AX7.1 kategorii jest poniżej. |

## <a name="enter-registration-ids-for-global-address-book-records"></a>Wprowadź identyfikatory rejestracji dla rekordów książki adresowej.
Książce adresowej (GAB) w programie Microsoft Dynamics 365 dla operacji zawiera informacje adresowe skonsolidowane dla odbiorców, dostawców, kontakty, relacji biznesowych i osoby prawne. Aby uzyskać więcej informacji, zobacz [omówienie książki adresowej](/dynamics365/operations/organization-administration/overview-global-address-book). Rekordy jednostek, które są przechowywane w globalnej książce adresowej może zawierać jeden lub więcej rekordów adresu. Adresy te są używane do różnych celów, takich jak płatności lub dostawy. Można skonfigurować rejestracji identyfikatorów dla informacji adresowych dla nabywców, dostawców, pracowników i osób prawnych. Strona (podmiot prawny, dostawcy, nabywcy, pracownik) nagrać, dla którego chcesz wprowadzić identyfikator rejestru, a następnie kliknij przycisk Znajdź **rejestracja nazwy** na formularzy związanych z partii, podmiot prawny, dostawcy, odbiorcy, pracownik, aby otworzyć **Zarządzanie adresami** strony. Na **podatku od rejestracji** kliknij przycisk **Dodaj**i wpisz następujące informacje dotyczące identyfikatora rejestracji.

|Pole                |opis                                                |
|---------------------|-----------------------------------------------------------|
| Typ rejestracji   | Typ rejestracji wybranego kraju/regionu.     |
| NIP | Identyfikatora rejestracji firmy.                                |
| opis         | Opis numer rejestracyjny.               |
| Sekcja             | Dodatkowe informacje o numer rejestracyjny. |
| Agencja wystawiająca      | Organ, który wydał numer rejestracyjny.        |
| Data wystawienia         | Data wystawienia numer rejestracyjny.              |
| Weszła w życie           | Data obowiązywania dla numer rejestracyjny.           |
| Data wygaśnięcia          | Data wygaśnięcia dla numerów rejestracyjnych.          |

> [!NOTE]
> Podatek, numer NIP danego podmiotu prawnego, dostawca, nabywca może zostać wybrany z rejestracji identyfikatorów powiązany identyfikator VAT i wprowadzony dla partii.

## <a name="search-for-records-by-registration-id"></a>Wyszukiwanie rekordów według Identyfikatora rejestracji
Wyszukiwanie rekordów jednostek na podstawie Identyfikatora rejestracji jest dostępny na formularzy związanych z partii, podmiot prawny, dostawcy, odbiorcy i pracownika. Kliknij **wyszukiwania identyfikator rejestracyjny** otworzyć **kryteria wyszukiwania identyfikator rejestracyjny** strony. Określ kryteria wyszukiwania i kliknij przycisk **znaleźć**. System wyświetli wybrane rekordy z książki adresowej i skojarzone typy rekordu jednostki.

## <a name="supported-registration-categories"></a>Kategorie obsługiwane rejestracji
Poniższa tabela zawiera listę typów obsługiwanych rejestracji w usłudze Dynamics 365 dla operacji. Użytkownicy zaznajomieni z polami systemu Microsoft Dynamics AX 2012 dla rejestracji identyfikatorów, ta tabela mapuje do 365 Dynamics dla operacji kategorie rejestracji tych pól.

| Dynamics 365 dla kategorii rejestracji operacji         |Kraj/region  | Pole/termin systemu Dynamics AX 2012|
|---------------------------------------------------------------|---------------------|---------------------------------|
| Identyfikator VAT                                                        | Wszystkie kraje Unii Europejskiej (UE)|  Numer identyfikacji podatkowej (ustawodawcze typu identyfikacji podatkowej w systemie AX2012 R3)|
| Identyfikator przedsiębiorstwa (COID)                                          | Belgia Republika Czeska Estonia Węgry Łotwa Litwa Polska Szwajcaria | Numer rejestracyjny przedsiębiorstwa numer (EnterpriseNumber) (RegNum\_W) numer rejestracyjny (RegNum\_W) numer rejestracyjny (RegNum\_W) numer rejestracyjny (RegNum\_W) numer rejestracyjny przedsiębiorstwa kodu (EnterpriseCode) (RegNum\_W) UID (typ ustawodawcze UID w systemie AX2012 R3) |
| Identyfikator oddziału                                                     | Belgia            | Numer oddziału (BranchNumber)|
| Kod Spisová (numer rejestracyjny wydawania agencji, sekcja) | Czechy     | Margines wewnętrzny numer Kept (CommercialRegisterInsetNumber) u handlowe zarejestrować sekcja rejestru handlowego (CommercialRegisterSection) (CommercialRegister)|
| Identyfikator odbiorcy cła                                           | Finlandia | Cło — numer odbiorcy (CustomsCustomerNumber\_FI)|
| NUMER IDENTYFIKACYJNY                                                           | Federacja Rosyjska| Numer identyfikacyjny (typ ustawodawcze INN w systemie AX2012 R3)|
| Kod przyczyny rejestracji                                                           | Federacja Rosyjska| Kod przyczyny rejestracji (typ ustawodawcze kod przyczyny rejestracji w systemie AX2012 R3)|
| KLASYFIKACJA OKDP                                                          | Federacja Rosyjska| Klasyfikacja OKDP (typ ustawodawcze OKDP w systemie AX2012 R3)|
| KLASYFIKACJA OKPO                                                          | Federacja Rosyjska| Klasyfikacja OKPO (typ ustawodawcze OKPO w systemie AX2012 R3)|
| RCOAD                                                         | Federacja Rosyjska| RCOAD (typ ustawodawcze RCOAD w systemie AX2012 R3)|
| PODSTAWOWY                                                          | Federacja Rosyjska| Podstawowy (ustawodawcze typ podstawowy w systemie AX2012 R3) |
| SNILS                                                         | Federacja Rosyjska| SNILS (typ ustawodawcze SNILS w systemie AX2012 R3)|
| CIFTS                                                         | Federacja Rosyjska| CIFTS (typ ustawodawcze CIFTS w systemie AX2012 R3)|

Aby uzyskać więcej informacji na temat rejestracji identyfikatorów przetwarzania, w tym wymagania wstępne, zobacz następujące nagrania zadania dla Identyfikatora VAT w cyklu życia usługi (LCS):

-   Konfigurowanie identyfikatora VAT
-   Numer NIP rejestracji dostawcy
-    Szukanie strony za pomocą identyfikatora VAT



