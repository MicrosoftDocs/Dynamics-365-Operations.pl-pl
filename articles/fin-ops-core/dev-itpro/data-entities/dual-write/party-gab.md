---
title: Książka adresowa strony i globalna książka adresowa
description: W tym temacie opisano funkcje aplikacji Party globalna książka adresowa funkcji podwójnego zapisu.
author: RamaKrishnamoorthy
ms.date: 04/25/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: 1e2dcfa69308f6691e787a1ff1893f9080dcaef1
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/05/2022
ms.locfileid: "8717454"
---
# <a name="party-and-global-address-book"></a>Książka adresowa strony i globalna książka adresowa

[!include [banner](../../includes/banner.md)]



*Strona* i *globalna książka adresowa* to pojęcia w aplikacjach finansowych i operacyjnych. Stroną może być osoba lub organizacja. Globalnie można przechowywać właściwości strony, takie jak nazwa, język, osoby kontaktowe i adresy, oraz zarządzać nimi. Gdy następnie wartość właściwości zmienia się w jednym miejscu, zmiana jest odzwierciedlona we wszystkich miejscach, w których uczestniczy strona.

## <a name="party"></a>Jednostka

Strona jest osobą lub organizacją zaangażowaną w działalność. Koncepcja strony sprawia, że osoba lub organizacja może odgrywać więcej niż jedną rolę (pracownik, klient, sprzedawca lub osoba kontaktowa) w firmie. Rola jest oparta na kontekście i celu. Oto kilka przykładów ról z dwóch fikcyjnych firm Contoso i Fabrikam:

+ **Pracownik** — pracownik etatowy. Przykładem jest pracownik etatowy firmy Contoso.
+ **Dostawca** — odnosi się do organizacji dostawcy lub jedynego właściciela, który dostarcza towary lub usługi firmie. Jeśli na przykład firma Fabrikam sprzedaje materiały do firmy Contoso, Fabrikam jest dostawcą Contoso.
+ **Osoba kontaktowa** — osoba kontaktowa. Na przykład jeśli firma Contoso kupuje materiały eksploatacyjne od firmy Fabrikam, pracownik firmy Contoso skontaktuje się z osobą kontaktową w firmie Fabrikam.
+ **Odbiorca** — to osoba lub firma, która kupuje różne produkty w firmie. Jeśli na przykład firma Contoso kupuje materiały od firmy Fabrikam, to firma Contoso jest klientem firmy Fabrikam.

Model strony jest często używany do reprezentowania średnich i złożonych relacji między organizacjami i osobami, zwłaszcza w przypadku, gdy strona pełni więcej niż jedną rolę. Oto kilka często występujących przykładów:

+ Stroną może być zarówno odbiorca, jak i dostawca. Na przykład w Ameryce Północnej firma Fabrikam sprzedaje firmie Contoso urządzenia elektryczne, a następnie kupuje głośniki od firmy Contoso. W Europie firma Fabrikam sprzedaje części do firmy Contoso, ale jeszcze nie kupuje z firmy Contoso.
+ Stroną może być zarówno pracownik, jak i klient. Na przykład pracownik firmy Contoso kupuje elektronikę w firmie Contoso na użytek osobisty.
+ Między osobą a organizacją może być relacja typu „wiele do wielu” (N:N). Na przykład firma Fabrikam udostępnia specjalistów wykonujących usługi i zatrudnia koordynatora przydziału. Ten koordynator przydziału dopasowuje specjalistów wykonujących usługi do żądań pracy od kilku klientów firmy Fabrikam. Contoso jest jednym z klientów firmy Fabrikam. Gdy firma Contoso potrzebuje specjalisty wykonującego usługę, kontaktuje się koordynatorem przydziału, który następnie realizuje żądanie. Ze względu na to, że koordynator przydziału obsługuje żądania wszystkich odbiorców, występuje relacja N:N.

Poniższa ilustracja przedstawia model danych strony.

![Model danych strony.](media/party-gab-image1.png)

> [!TIP]
> Podczas tworzenia nowego rekordu konta użyj pola **Strona**, aby wyszukać rekord według nazwy. W ten sposób po odnalezieniu rekordu wystarczy go wybrać. System następnie automatycznie wstawia wszystkie dane strony. Nie musisz ręcznie ustawiać wszystkich wymaganych pól. Tak zachowują się gotowe strony **Konto**, **Osoba kontaktowa** i **Dostawca**.

Dwukrotny zapis nie obsługuje wszystkich ról strony w aplikacjach finansowych i operacyjnych. Aby uzyskać pełną listę ról stron, zobacz [Omówienie globalnej książki adresowej](../../../fin-ops/organization-administration/overview-global-address-book.md).

### <a name="global-address-book"></a>Globalna książka adresowa

Globalna książka adresowa jest katalogiem adresów pocztowych i elektronicznych organizacji i osób uczestniczących w działalności.

Globalna książka adresowa przechowuje i obsługuje tyle adresów pocztowych, jak i elektronicznych, ile jest wymaganych. Przypuśćmy na przykład, że firma Fabrikam ma stacje benzynowe w 50 lokalizacjach. Każda lokalizacja ma inny adres pocztowy, adres e-mail i numer telefonu. Wszystkie zakupy biznesowe są rozliczane na głównej stacji benzynowej, ale są wysyłane bezpośrednio do określonej stacji, która wnioskowała o zakup. Globalna książka adresowa przechowuje główną stację benzynową jako adres rozliczeniowy firmy Fabrikam, a poszczególne stacje benzynowe jako adres wysyłkowy. Adresy mogą zostać zapisane raz i stosownie do potrzeb wczytywane do ofert i zamówień.

W zależności od kontekstu biznesowego osoba lub organizacja może pełnić więcej niż jedną rolę, a dla wszystkich tych ról może być używany ten sam adres pocztowy i adres elektroniczny. W takim przypadku zmiana adresu w jednej roli powinna się pojawiać we wszystkich innych. Firmowa globalna książka adresowa obsługuje adresy globalnie.

Na poniższej ilustracji przedstawiono model danych globalnej książki adresowej.

![Model danych globalnej książki adresowej.](media/party-gab-image2.png)

## <a name="contact"></a>Kontakt

W aplikacjach do obsługi klienta osoba kontaktowa jest osobą. Jednak tabela **Osoba kontaktowa** została przeciążona, aby reprezentować osobę, użytkownika portalu, klienta B2C lub dostawcę. Reprezentacja jest niejawna i nie można dostrzec różnicy bez badania transakcji powiązanych. Tabela **Osoba kontaktowa** została ograniczona do relacji jeden do jednego (1:1) z tabelą **Konto**. W ramach modelu strony i globalnej książki adresowej podwójny zapis wprowadza jawne właściwości klasyfikacji oraz umożliwia relacje N:N między osobą kontaktową a organizacją (jednostka **Konto** lub **Dostawca**).

Istnieją dwa typy wierszy **Kontakt**:

+ **Rozłożony kontakt** — wiersz **Osoba kontaktowa** z wartością obowiązkową w polu **Firma**.
+ **Nierozłożony kontakt** — wiersz **Osoba kontaktowa** z pustym polem **Firma**.

W tabeli **Osoby kontaktowe** mogą być przechowywane następujące typy wierszy.

| Typ wiersza | opis |
|----------|-------------|
| Osoba, która jest klientem (na przykład osobą kontaktową do sprzedaży lub klientem B2C) | Rekord rozłożonego kontaktu, w którym pole **Firma** nie jest puste, a pole **Jest klientem** ma wartość **Tak**. |
| Osoba, która jest na dostawcą (na przykład jedynym właścicielem, jak dostawcą) | Rekord rozłożonego kontaktu, w którym pole **Firma** nie jest puste, a pole **Jest dostawcą** ma wartość **Tak**. |
| Osoba będąca jednocześnie klientem i dostawcą | Rekord rozłożonego kontaktu, w którym pole **Firma** nie jest puste, a pole **Jest klientem** ma wartość **Tak**, a pole **Jest dostawcą** jest ustawione na **Tak**. Osoba może być zarówno producentem jednego produktu, jak i konsumentem innego produktu. Zarówno aplikacje finansowe i operacyjne, jak i funkcja podwójnego zapisu obsługują tę relację. |
| Osoba, która jest osobą kontaktową organizacji, ale nie jest klientem ani dostawcą | Rekord nierozłożonego kontaktu, w którym pole **Firma** nie jest puste, a pole **Jest klientem** ma wartość **Nie**, a pole **Jest dostawcą** jest ustawione na **Nie**. |

## <a name="contact-for-party-table"></a>Tabela Osoba kontaktowa strony

Tabela **Osoba kontaktowa strony** przechowuje i obsługuje relacje N:N między wierszami **Konto** i **Osoba kontaktowa**. Może odfiltrować rozłożone wiersze **Osoba kontaktowa** od nierozłożonych i skojarzyć tylko nierozłożone wiersze **Osoba kontaktowa** z wierszami **Konto** lub **Dostawca**.

Na przykład Natasha Jones i Miguel Reyes są weterynarzami, którzy zapewniają opiekę na farmach na swoich obszarach. Natasha obsługuje rejon Seattle, a Miguel rejon Kent. W aplikacji obsługi klienta farmy są reprezentowane jako odbiorcy, a weterynarze są reprezentowane jako osoby kontaktowe. Pojedynczy rekord osoby **kontaktowej** dla Natasha jest skojarzony ze wszystkimi osobami, z które pracuje Natasha. Analogicznie, pojedynczy rekord **Osoba kontaktowa** Miguela jest skojarzony ze wszystkimi osobami, z które pracuje Miguel.

Te relacje są przechowywane w tabeli **Osoba kontaktowa dla strony**. Te informacje znajdują się na gotowych stronach **Konto**, **Osoba kontaktowa** i **Dostawca**:

+ Na stronie **Konto** można użyć karty **Skojarzone kontakty** w celu skojarzenia jednego lub większej liczby kontaktów z wierszem **Konto**. W ten sposób przypisujesz osoby kontaktowe do organizacji. Następnie można wybrać jedną osobę kontaktową jako główną dla konta. W przypadku korzystania ze strony **Szybkie tworzenie** można tylko wybrać osobę kontaktową. Działanie jest takie same w przypadku korzystania ze strony **Dostawca** i gdy typem rekordu jest **Organizacja**.
+ Na stronie **Osoba kontaktowa**, jeśli wiersz zawiera dane odbiorcy, dostawcy lub obu (rozłożony kontakt), na karcie **Skojarzone kontakty** można skojarzyć jedną lub więcej osób kontaktowych. W ten sposób przypisujesz osoby kontaktowe dla klienta lub dostawcy B2C. Następnie można wybrać jedną osobę kontaktową jako główną. W przypadku korzystania ze strony **Szybkie tworzenie** można tylko wybrać osobę kontaktową.
+ Na stronie **Osoba kontaktowa**, jeśli wiersz jest osobą kontaktową (nierozłożony kontakt), na karcie **Skojarzone organizacje** można skojarzyć jednego lub więcej odbiorców lub dostawców. W ten sposób przypisujesz odbiorców lub dostawców do ich osoby kontaktowej. Odbiorca lub dostawca może być organizacją, osobą lub obiema organizacjami. W danym momencie można wybrać wartość tylko jednego z czterech pól:

    + Jeśli wybierzesz wartość w polu **Identyfikator strony**, kontakt źródłowy jest przypisany do wszystkich ról wybranej strony.
    + W przypadku wybrania wartości w polu **Skojarzony kontakt** wybierasz rozłożony kontakt typu **Osoba kontaktowa**.
    + W przypadku wybrania wartości w polu **Skojarzone konto** lub **Skojarzony dostawca** wybierasz organizację.

    ![Karta Skojarzone organizacje na stronie Osoba kontaktowa.](media/party-gab-image3.png)

    Niezależnie od wyboru, skojarzenie jest tworzone na poziomie jednostki i ma zastosowanie do wszystkich ról jednostki i jest przechowywane w jednostce **Osoba kontaktowa strony**.

> [!NOTE]
> Nazwa wyświetlana tabeli **Osoba kontaktowa strony** w aplikacjach obsługi klienta to **Kontakt dla odbiorcy/dostawcy**.

Po otwarciu wiersza **Osoba kontaktowa**, w którym pole **Jest klientem** i pole **Jest dostawcą** ma wartość **Nie**, zostanie wyświetlona karta **Skojarzone organizacje**. Ta karta umożliwia skojarzenie organizacji odbiorcy lub dostawcy z osobą kontaktową.

Po otwarciu wiersza **Osoba kontaktowa**, w którym pole **Jest klientem** lub pole **Jest dostawcą** ma wartość **Tak**, zostanie wyświetlona karta **Skojarzone kontakty**. Ta karta służy do skojarzenia jednego lub większej liczby kontaktów.

## <a name="postal-addresses"></a>Adresy pocztowe

Wprowadzono nową kartę o nazwie **Adresy** w stronach **Konto**, **Kontakt** i **Dostawca**. Ta karta obsługuje wiele adresów pocztowych przy użyciu siatki, tak jak pokazano na poniższej ilustracji.

![Siatka adresów pocztowych.](media/party-gab-image4.png)

Siatka zawiera następujące kolumny:

+ **Role adresu pocztowego** — cel adresu pocztowego.
+ **Jest adresem podstawowym** — wartość wskazująca, czy adres jest adresem podstawowym.
+ **Numer adresu** — kolejność adresu.

Przycisk **Nowy adres** nad siatką pozwala utworzyć dowolną liczbę adresów pocztowych.

Pola **Adres 1** i **Adres 2** na karcie **Podsumowanie** strony **Konto** odpowiadają odpowiednio adresom **Dostawy** i **Faktury**.

![Karta Podsumowanie adresów pocztowych.](media/party-gab-image5.png)

Pola **Adres 1**, **Adres 2** i **Adres 3** na karcie **Podsumowanie** strony **Osoba kontaktowa** odpowiadają odpowiednio adresom **Biznesowemu**, **Dostawy** i **Faktury**.

## <a name="electronic-addresses"></a>Adresy elektroniczne

Wprowadzono nową kartę o nazwie **Adresy elektroniczne** w stronach **Konto**, **Kontakt** i **Dostawca**. Ta karta obsługuje wiele adresów elektronicznych przy użyciu siatki, tak jak pokazano na poniższej ilustracji.

![Siatka adresów elektronicznych.](media/party-gab-image6.png)

Siatka zawiera następujące kolumny:

+ **Typ** — typ adresu elektronicznego.
+ **Jest adresem podstawowym** — wartość wskazująca, czy adres jest adresem podstawowym.
+ **Cel** — cel adresu elektronicznego.

Przycisk **Nowy adres elektroniczny** nad siatką pozwala utworzyć dowolną liczbę adresów elektronicznych.

Podczas procesu kwalifikacji potencjalnego klienta można podać numer telefonu służbowego i numer telefonu komórkowego. Numer telefonu służbowego jest traktowany jako podstawowy, jeśli **IsMobile=No**, a numer telefonu komórkowego jest traktowany jako pomocniczy, jeśli **IsMobile=Yes**.

> [!TIP]
> Do zarządzania adresami pocztowymi i elektronicznymi służą karty **Adresy** i **Adresy elektroniczne** na formularzach **Konto** i **Kontakt**. Zapewnia to synchronizację danych adresowych z aplikacjami finansowymi i operacyjnymi.

## <a name="setup"></a>Konfiguracja

1. Otwórz środowisko aplikacji z obsługą klienta.

2. Zainstaluj wszystkie wstępnie wymagane rozwiązania, zgodnie z opisem w [Osobny pakiet Aranżacja aplikacji Podwójny zapis](separated-solutions.md).

3. Zainstaluj [rozwiązania z podwójnym zapisem i globalna książka adresowa](https://aka.ms/dual-write-gab).

4. Otwórz klienta rozwiązania Finanse i Działania. Przejdź do modułu Zarządzanie danymi i wybierz kartę Podwójny zapis. Zostanie otwarta strona administracji podwójnego zapisu.

5. Zastosuj oba rozwiązania zainstalowane w krokach 2 i 3, używając funkcji [Zastosuj rozwiązanie](link-your-environment.md).

6. Zatrzymaj poniższe mapy, ponieważ nie są one już wymagane. Zamiast tego uruchom mapę `Contacts V2 (msdyn_contactforparties)`.

    + Kontakty CDS w wersji 2 i kontakty (odwołanie do kontaktów odbiorcy)
    + Kontakty CDS w wersji 2 i kontakty (odwołanie do kontaktów dostawcy)

7. Następujące mapowania jednostek są aktualizowane dla funkcji jednostki, więc do tych mapowań musi zostać zastosowana najnowsza wersja.

    Mapa | Aktualizuj do tej wersji | Zmiany
    ---|---|---
    `CDS Parties (msdyn_parties)`| 1.0.0.2 | To jest nowa mapa dodawana jako część wersji.
    `Contacts V2 (msdyn_contactforparties)`| 1.0.0.6 | To jest nowa mapa dodawana jako część wersji.
    `Customers V3 (accounts)` | 1.0.0.5 |Usunięto `PartyNumber` i inne pola powiązane z stroną, takie jak nazwa, dane osobowe, pola adresu pocztowego i elektroniczny adres kontaktowy.
    `Customer V3 (contacts)` | 1.0.0.5 | Usunięto `PartyNumber` i inne pola powiązane z stroną, takie jak nazwa, dane osobowe, pola adresu pocztowego i elektroniczny adres kontaktowy.
    `Vendors V2 (msdyn_vendors)` | 1.0.0.6 | Usunięto `PartyNumber` i inne pola powiązane z stroną, takie jak nazwa, dane osobowe, pola adresu pocztowego i elektroniczny adres kontaktowy.
    `CDS Sales quotation headers (quotes)` | 1.0.0.7 | Zamieniono osobę kontaktowa na odwołanie `ContactforParty`.
    `Sales invoice headers V2 (invoices)` | 1.0.0.4 | Zamieniono osobę kontaktowa na odwołanie `ContactforParty`.
    `CDS Sales order headers (salesorders)` | 1.0.0.5 | Zamieniono osobę kontaktowa na odwołanie `ContactforParty`.
    `CDS Party postal address locations (msdyn_partypostaladdresses)` | 1.0.0.1  | To jest nowa mapa dodawana jako część wersji.
    `CDS postal address history V2 (msdyn_postaladdresses)` | 1.0.0.2 | To jest nowa mapa dodawana jako część wersji.
    `CDS postal address locations (msdyn_postaladdresscollections)` | 1.0.0.0 | To jest nowa mapa dodawana jako część wersji.
    `Party Contacts V3 (msdyn_partyelectronicaddresses)` | 1.0.0.0 | To jest nowa mapa dodawana jako część wersji.
    `Complimentary Closings (msdyn_compliemntaryclosings)` | 1.0.0.0 | To jest nowa mapa dodawana jako część wersji.
    `Decision making roles (msdyn_decisionmakingroles)` | 1.0.0.0 | To jest nowa mapa dodawana jako część wersji.
    `Loyalty levels (msdyn_loyaltylevels)` | 1.0.0.0 | To jest nowa mapa dodawana jako część wersji.
    `Contact person titles (msdyn_salescontactpersontitles)` | 1.0.0.0 | To jest nowa mapa dodawana jako część wersji.
    `Personal character types (msdyn_personalcharactertypes)` | 1.0.0.0 | To jest nowa mapa dodawana jako część wersji.
    `Salutations (msdyn_salutations)` | 1.0.0.0 | To jest nowa mapa dodawana jako część wersji.
    `Employment job functions (msdyn_employmentjobfunctions)` | 1.0.0.0 | To jest nowa mapa dodawana jako część wersji.
    `CDS Address roles (msdyn_addressroles)` | 1.0.0.0 | To jest nowa mapa dodawana jako część wersji.

8. Przed uruchomieniem powyższych map należy ręcznie zaktualizować klucze integracji, zgodnie z poniższymi instrukcjami. Następnie kliknij przycisk **Zapisz**.

    | Mapa | Klucze |
    |-----|------|
    | Konto |  accountnumber [Numer konta]<br>msdyn_company.cdm_companycode [Firma (kod firmy)] |
    | Kontakt | msdyn_contactpersonid [Numer konta / Identyfikator osoby kontaktowej]<br>msdyn_company.cdm_companycode [Firma (kod firmy)] |
    | Osoba kontaktowa dla odbiorcy/dostawcy | msdyn_contactforpartynumber [Numer osoby kontaktowej strony]<br>msdyn_associatedcompanyid.cdm_companycode [Skojarzona firma (kod firmy)] |
    | Dostawca | msdyn_vendoraccountnumber [Numer konta dostawcy]<br>msdyn_company.cdm_companycode [Firma (kod firmy)]|

9. W Dataverse limity znaków reguł wykrywania duplikatów zostały zwiększone z 450 do 700 znaków. Ten limit umożliwia dodanie jednego lub większej liczby kluczy do reguł wykrywania duplikatów. Rozwiń regułę wykrywania duplikatów dla tabeli **Konta**, aby ustawić następujące pola.

    | Pole | Wartość |
    |-------|-------|
    | Imię i nazwisko | Konta o takiej samej nazwie konta. |
    | opis | Wykrywa rekordy konta o tej samej wartości w atrybucie Nazwa konta. |
    | Podstawowy typ rekordu | Konto |
    | Pasujący typ rekordu | Konto |
    | Nazwa konta (pole) | Dokładne dopasowanie |
    | Firma (pole) | Dokładne dopasowanie |
    | Typ relacji (pole) | Dokładne dopasowanie |
    | Identyfikator strony (pole) | Dokładne dopasowanie |
    | Wybierz (pole) | (puste) |

    ![Duplikuj regułę dla kont.](media/duplicate-rule-1.PNG)

10. Rozwiń regułę wykrywania duplikatów dla tabeli **Osoby kontaktowe**, aby ustawić następujące pola.

    | Pole | Wartość |
    |-------|-------|
    | Imię i nazwisko | Kontakty z tym samym imieniem i nazwiskiem. |
    | opis | Wykrywa rekordy osoby kontaktowej o takich samych wartościach w polach Imię i Nazwisko. |
    | Podstawowy typ rekordu | Kontakt |
    | Pasujący typ rekordu | Kontakt |
    | Imię (pole) | Dokładne dopasowanie |
    | Nazwisko (pole) | Dokładne dopasowanie |
    | Firma (pole) | Dokładne dopasowanie |
    | Identyfikator strony (pole) | Dokładne dopasowanie |
    | Wybierz (pole) | (puste) |

    ![Duplikuj regułę dla osób kontaktowych.](media/duplicate-rule-2.PNG)

11. Jeśli jesteś istniejącym użytkownikiem podwójnego zapisu, postępuj zgodnie z instrukcjami w sekcji [Uaktualnienie do modelu strony i globalnej książki adresowej](upgrade-party-gab.md) i uaktualnij dane. **Nie kontynuuj do kroku 12 bez wykonania tego kroku.** Jeśli jesteś nowym użytkownikiem podwójnego zapisu, przejdź do kroku 12.

12. Jeśli jesteś istniejącym użytkownikiem podwójnego zapisu, wykonaj krok 11, a następnie możesz uruchamiać mapy w następującej kolejności. Jeśli jesteś nowym klientem z podwójnym zapisem, możesz przejść bezpośrednio. Jeśli zostanie wyświetlony komunikat o błędzie z informacją „Negatywny wynik sprawdzania poprawności projektu. Brak pola docelowego", otwórz mapę i wybierz polecenie **Odśwież tabele**, a następnie uruchom mapę.

    Aplikacje finansowe i operacyjne | Aplikacja Customer Engagement  
    ----------------------------|------------------------
    [Strony usługi CDS](mapping-reference.md#220) | msdyn_parties
    [Lokalizacje adresu pocztowego usługi CDS](mapping-reference.md#234) | msdyn_postaladdresscollections
    [Historia adresu pocztowego usługi CDS V2](mapping-reference.md#235) | msdyn_postaladdresses
    [Lokalizacje adresu pocztowego strony usługi CDS](mapping-reference.md#233) | msdyn_partypostaladdresses
    [Osoby kontaktowe strony wer. 3](mapping-reference.md#236) | msdyn_partyelectronicaddresses
    [Odbiorcy (wersja 3)](mapping-reference.md#101) | Konta
    [Odbiorcy (wersja 3)](mapping-reference.md#116) | kontakty
    [Dostawcy wersja 2](mapping-reference.md#202) | msdyn_vendors
    [Tytuły osoby kontaktowej](mapping-reference.md#223) | msdyn_salescontactpersontitles
    [Formuły grzecznościowe](mapping-reference.md#222) | msdyn_complimentaryclosings
    [Zwroty grzecznościowe](mapping-reference.md#228) | msdyn_salutations
    [Role podejmujące decyzje](mapping-reference.md#224) | msdyn_decisionmakingroles
    [Funkcje stanowisk zatrudnienia](mapping-reference.md#225) | msdyn_employmentjobfunctions
    [Poziomy lojalności](mapping-reference.md#226) | msdyn_loyaltylevels
    [Typy osób](mapping-reference.md#227) | msdyn_personalcharactertypes
    [Kontakty wersja 2](mapping-reference.md#221) | msdyn_contactforparties
    [Nagłówek oferty sprzedaży CDS](mapping-reference.md#215) | Cytaty
    [Nagłówki zamówień sprzedaży CDS](mapping-reference.md#217) | salesorders
    [Nagłówki faktur sprzedaży wer. 2](mapping-reference.md#118) | faktury
    [Role adresów CDS](mapping-reference.md#301) | msdyn_addressroles

> [!NOTE]
> Mapa `CDS Contacts V2 (contacts)` jest mapą zatrzymaną w kroku 1. Podczas próby uruchomienia innych map te 2 mapy mogą pojawiać się na liście zależnych. Nie uruchamiaj tych map.
>
> Jeśli zainstalowano rozwiązanie strony i globalnej książki adresowej, musisz wyłączyć wtyczkę o nazwie `Microsoft.Dynamics.SCMExtended.Plugins.Plugins.LeadPrimaryContactPostCreate: QualifyLead of lead`. Jeśli odinstalujesz rozwiązanie strony i globalnej książki adresowej, musisz ponownie włączyć tę wtyczkę.
>
> Pole `msdyn_*partynumber` (jednowierszowe pole tekstowe) zawarte w tabelach **Konto**, **Osoba kontaktowa** i **Dostawca** w przyszłości zostanie wycofane z użytku. Nazwa etykiety ma prefiks **(przestarzały)**, aby to zaznaczyć. Zamiast tego użyj pola **msdyn_partyid**. To pole jest polem wyszukiwania tabeli **msdyn_party**.
>
> Nazwa tabeli | Stare pole | Nowe pole
> --------|-------|--------
> Konto | `msdyn_partynumber` | `msdyn_partyid`
> Kontakt | `msdyn_partynumber` | `msdyn_partyid`
> msdyn_vendor | `msdyn_vendorpartynumber` | `msdyn_partyid`

## <a name="templates"></a>Szablony

Zbiór map tabel współpracuje ze sobą na potrzeby interakcji między stronami i globalną książką adresową, jak pokazano w poniższej tabeli.

| Aplikacje finansowe i operacyjne | Aplikacja Customer Engagement | Opis |
|----------------------------|-------------------------|-------------|
| [Tytuły osoby kontaktowej](mapping-reference.md#223) | msdyn\_salescontactpersontitles |
| [Odbiorcy (wersja 3)](mapping-reference.md#101) | Konta |
| [Odbiorcy (wersja 3)](mapping-reference.md#116) | kontakty |
| [Strony usługi CDS](mapping-reference.md#220) | msdyn\_parties |
| [Lokalizacje adresu pocztowego strony usługi CDS](mapping-reference.md#233) | msdyn\_partypostaladdresses |
| [Historia adresu pocztowego usługi CDS V2](mapping-reference.md#235) | msdyn\_postaladdresses |
| [Lokalizacje adresu pocztowego usługi CDS](mapping-reference.md#234) | msdyn\_postaladdresscollections |
| [Nagłówek oferty sprzedaży CDS](mapping-reference.md#215) | Cytaty |
| [Nagłówki zamówień sprzedaży CDS](mapping-reference.md#217) | salesorders |
| [Formuły grzecznościowe](mapping-reference.md#222) | msdyn\_complimentaryclosings |
| [Kontakty wersja 2](mapping-reference.md#221) | msdyn\_contactforparties |
| [Role podejmujące decyzje](mapping-reference.md#224) | msdyn\_decisionmakingroles |
| [Funkcje stanowisk zatrudnienia](mapping-reference.md#225) | msdyn\_employmentjobfunctions |
| [Poziomy lojalności](mapping-reference.md#226) | msdyn\_loyaltylevels |
| [Osoby kontaktowe strony wer. 3](mapping-reference.md#236) | msdyn\_partyelectronicaddresses |
| [Typy osób](mapping-reference.md#227) | msdyn\_personalcharactertypes |
| [Nagłówki faktur sprzedaży wer. 2](mapping-reference.md#118) | faktury |
| [Zwroty grzecznościowe](mapping-reference.md#228) | msdyn\_salutations |
| [Dostawcy wersja 2](mapping-reference.md#202) | msdyn\_vendors |
| [Role adresów CDS](mapping-reference.md#301) |msdyn\_addressroles|

Aby uzyskać więcej informacji, zobacz [Odniesienie do mapowania z podwójnym zapisem](mapping-reference.md).

## <a name="address-roles-as-a-multi-select-drop-down-list"></a>Role w adresach jako lista rozwijana wybierana wiele elementów
Adres pocztowy lub adres elektroniczny może służyć do więcej niż jednego celu. Adres pocztowy może na przykład pełnić zarówno funkcję adresu bilingowego, jak i adresu dostawy. W takich przypadkach użytkownik może wybrać z listy rozwijanej zarówno **Fakturę**, jak i **Dostawę**, jak pokazano na poniższej ilustracji. 

![Lista rozwijana Cel/Rola.](media/purpose.png)

## <a name="known-issues-and-limitations"></a>Znane problemy i ograniczenia

+ W aplikacjach finansowych i operacyjnych podczas tworzenia odbiorcy wraz z adresem i zapisywania go adres może nie być synchronizowany z tabelą **Adres**. Jest to spowodowane problemem z harmonogramem platformy podwójnego zapisu. Aby obejść ten problem należy najpierw utworzyć odbiorcę, a następnie go zapisać. Następnie dodaj adres.
+ W aplikacjach finansowych i operacyjnych, gdy rekord odbiorcy ma adres podstawowy i tworzysz nowy kontakt dla tego odbiorcy, rekord osoby kontaktowej dziedziczy adres podstawowy ze skojarzonego rekordu odbiorcy. Dzieje się tak również w przypadku osoby kontaktowej dostawcy. Dataverse obecnie nie obsługuje tego działania. Jeśli jest włączona funkcja podwójnego zapisu, osoby kontaktowe odbiorcy dziedziczone z adresu podstawowego z aplikacji finansowych i operacyjnych są synchronizowane z Dataverse razem ze swoim adresem.
+ W aplikacjach finansowych i operacyjnych możesz utworzyć rekord osoby kontaktowej za pomocą formularza **Dodaj osobę kontaktową**. Podczas próby utworzenia nowej osoby kontaktowej z formularza **Wyświetl osobę kontaktową** akcja nie powiedzie się. Jest to znany problem.

    ![Znany problem z dodawania osoby kontaktowej.](media/party-gab-contact-issue.png)

+ **Synchronizacja początkowa** nie obsługuje pól czasu **Dostępny od** i **Dostępny do** w tabeli **Osoba kontaktowa dla strony**, ponieważ DIXF konwertuje wartość na ciąg, a nie liczbę całkowitą. Konwersja wywołuje błąd `Cannot convert the literal '<say 08:00:00>' to the expected type edm.int32`.
+ Nie można wprowadzić adresu pocztowego z datą w przyszłości, używając aplikacji finansowych i operacyjnych z podwójnym zapisem, ponieważ Dataverse nie obsługuje ważności daty. Jeśli użytkownik wpisze w aplikacjach finansowych i operacyjnych adres pocztowy z datą w przyszłości, zostanie on w pełni zsynchronizowany z Dataverse i natychmiast zobaczysz adres w interfejsie użytkownika. Wszelkie aktualizacje tego rekordu będą powodować błąd, ponieważ ma on datę przyszłą, a nie bieżącą w aplikacji finansowej i operacyjnej.
