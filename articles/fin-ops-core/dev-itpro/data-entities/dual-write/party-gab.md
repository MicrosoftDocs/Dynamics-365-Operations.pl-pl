---
title: Książka adresowa strony i globalna książka adresowa
description: W tym temacie opisano funkcje aplikacji Party globalna książka adresowa funkcji podwójnego zapisu.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
ms.service: dynamics-ax-applications
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: e7bec58f8094a1448017822e7d8840368cc482b8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750795"
---
# <a name="party-and-global-address-book"></a>Książka adresowa strony i globalna książka adresowa

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Osobista i globalna książka adresowa to pojęcia w aplikacjach Finance and Operations. Stroną może być osoba lub organizacja. Globalnie można przechowywać właściwości **strony**, takie jak nazwa, język, kontakty i adresy, oraz zarządzać nimi. Gdy wartość właściwości zmienia się w jednym miejscu, odzwierciedla ją we wszystkich miejscach, w których uczestniczy **strona**.

## <a name="party"></a>Jednostka

*Strona* jest osobą lub organizacją zaangażowaną w działalność. Korzystając z koncepcji Strony, osoba lub organizacja może odgrywać więcej niż jedną rolę (pracownik, klient, sprzedawca lub kontakt) w firmie. Rola jest oparta na kontekście i celu. Oto kilka przykładów z dwóch fikcyjnych firm Contoso i Fabrikam.

+ **Pracownik**: pracownik etatowy. Na przykład pracownik firmy Contoso.
+ **Dostawca**: odnosi się do organizacji dostawcy lub jedynego właściciela, który dostarcza towary lub usługi firmie. Jeśli na przykład firma Fabrikam sprzedaje materiały do firmy Contoso, w rolę dostawcy pełni firma Fabrikam.
+ **Osoba kontaktowa**: osoba kontaktowa. Na przykład jeśli firma Contoso kupuje materiały eksploatacyjne od firmy Fabrikam, pracownik firmy Contoso skontaktuje się z osobą kontaktową w firmie Fabrikam.
+ **Odbiorca**: odbiorca to osoba lub firma, która kupuje różne produkty w firmie. Jeśli na przykład firma Contoso kupuje materiały od firmy Fabrikam, to firma Contoso jest klientem firmy Fabrikam.

Model strony jest często używany do reprezentowania średnich i złożonych relacji między organizacjami i osobami, zwłaszcza w przypadku, gdy strona pełni więcej niż jedną rolę. Oto kilka często występujących przykładów:

+ Stroną może być zarówno odbiorca, jak i dostawca. Na przykład w Ameryce Północnej firma Fabrikam sprzedaje firmie Contoso urządzenia elektryczne, a następnie kupuje głośniki od firmy Contoso. W Europie firma Fabrikam sprzedaje części do firmy Contoso, ale jeszcze nie kupuje z firmy Contoso.
+ Stroną może być zarówno pracownik, jak i klient. Na przykład pracownik firmy Contoso kupuje elektronikę w firmie Contoso na użytek osobisty.
+ Między osobą a organizacją może być relacja typu „wiele do wielu”. Na przykład firma Fabrikam dostarcza usługi i zatrudnia koordynatora miejsca. Ten kierownik pasuje do usługi, która odpowiada na żądania pracy kilku klientów firmy Fabrikam. Firma Contoso jest jednym z kont odbiorcy. Gdy firma Contoso potrzebuje specjalisty, firma Contoso kontaktuje się ze specjalistą, który następnie ułatwia to żądanie. Koordynator obsługuje żądania dotyczące wszystkich odbiorców, tworząc relację typu „wiele do wielu”.

Poniższy obraz przedstawia model danych dla strony:

![Model danych dla stron](media/party-gab-image1.png)

> [!Tip]
> Podczas próby utworzenia nowego rekordu konta użyj pola „Strona”, aby wyszukać rekord według nazwy. W przypadku odnalezienia rekordu wystarczy go wybrać. System automatycznie wypełnia wszystkie dane strony. Nie trzeba ręcznie wprowadzać wszystkich wymaganych pól. To działanie można znaleźć poza polem wyboru w formularzach Konto, Kontakt i Dostawca.

Nie wszystkie role firm w aplikacjach Finance and Operations są obsługiwane w przypadku podwójnego zapisu. Aby uzyskać pełną listę ról stron, zobacz [Omówienie globalnej książki adresowej](../../../fin-ops/organization-administration/overview-global-address-book.md).

### <a name="global-address-book"></a>Globalna książka adresowa

Ten globalna książka adresowa jest katalogiem adresów pocztowych i elektronicznych organizacji i osób uczestniczących w działalności gospodarczej.

System globalna książka adresowa przechowuje i obsługuje tyle adresów pocztowych, jak i elektronicznych. Przypuśćmy na przykład, że firma Fabrikam ma stacje gazu w 50 lokalizacjach. Każda lokalizacja ma inny adres pocztowy, adres e-mail i numer telefonu. Wszystkie zakupy biznesowe są rozliczane na głównej stacji gazu, ale są wysyłane bezpośrednio do określonej stacji paliwowej, która wnioskowała o zakup. Globalna książka adresowa przechowuje główną stację benzynową jako adres rozliczeniowy, a każdą stację benzynową jako adres wysyłki dla firmy Fabrikam. Adresy mogą być przechowywane raz i w razie potrzeby wczytywane do ofert i zamówień.

Osoba lub organizacja może pełnić więcej niż jedną rolę w zależności od kontekstu biznesowego. W takim przypadku adresy pocztowe i adresy elektroniczne mogą być takie same. W takim przypadku zmiana adresu w jednej roli powinna się pojawiać w drugiej roli i na odwrót. Firmowa globalna książka adresowa obsługuje adresy globalnie.

![Model danych dla globalnej książki adresowej](media/party-gab-image2.png)

## <a name="contacts"></a>Kontakty

W aplikacjach do obsługi klienta *Kontakt* jest osobą. Jednak tabela **Kontakty** została przeciążona, aby reprezentować osobę, użytkownika portalu, klienta B2C lub dostawcę. Reprezentacja jest niejawna i nie można odróżnić tej różnicy bez konieczności badania transakcji powiązanych. Tabela **Kontakt** została ograniczona do relacji 1:1 z tabelą **Konta**. W ramach modelu strony i globalna książka adresowa podwójny zapis wprowadza jawne właściwości klasyfikacji, a przy dwóch zapisach są określone relacje N:N między **osobą kontaktową** a organizacją (jednostka konto lub jednostka Dostawca).

Istnieją dwa typy wierszy **Kontakt**:

+ Rozłożony kontakt — wiersz kontaktu z wartością obowiązkową w polu **Firma**.
+ Niesprawowany kontakt — wiersz osoby kontaktowej z pustym polem **Firmy** pustym.

W tabeli **Osoby kontaktowe** mogą być przechowywane następujące typy wierszy:

Typ wiersza | opis
---|---
Osoba, która jest klientem, na przykład kontaktem do sprzedaży lub klientem B2C. | Rekord rozłożonego kontaktu, w którym pole **Firma** nie jest puste, a pole **Jest klientem** ma wartość **Tak**.
Osoba, która jest na przykład dostawcą, jedynym właścicielem, np. dostawcą. | Rekord rozłożonego kontaktu, w którym pole **Firma** nie jest puste, a pole **Jest dostawcą** ma wartość **Tak**.
Osoba będąca jednocześnie klientem i sprzedawcą. | Rekord rozłożonego kontaktu, w którym pole **Firma** nie jest puste, a pole **Jest klientem** ma wartość **Tak**, a pole **Jest dostawcą** jest ustawione na **Tak**. Osoba może być zarówno producentem jednego produktu, jak i konsumentem innego produktu. Ta relacja obsługuje zarówno aplikacje Finance and Operations, jak i podwójnego zapisu.
Osoba, która jest osobą kontaktową organizacji, ale nie jest klientem ani dostawcą. | Rekord nierozłożonego kontaktu, w którym pole **Firma** nie jest puste, a pole **Jest klientem** ma wartość **Nie**, a pole **Jest dostawcą** jest ustawione na **Nie**.

## <a name="contact-for-party"></a>Osoba kontaktowa strony

**Kontakt dla sklepów strony** i obsługa relacji N:N między wierszami **Konta** i wierszami **Kontaktów**. Może odfiltrować rozłożone wiersze **osoby kontaktowej** z niesprawowanych wierszy i skojarzyć tylko niezaszepowane wiersze **kontaktu** z wierszami **Konto** lub **Dostawca**.

Na przykład Natasha Jones i Miguel Reyes są weterynarzami, którzy zapewniają opiekę na farmach na swoich obszarach. Natasha znajduje się w obszarze Seattle, a następnie w obszarze Kent. W aplikacji służącej do relacji z klientami osoba kontaktowa jest reprezentowana jako odbiorcy, a osoby te są osobami kontaktowymi. Pojedynczy rekord osoby **kontaktowej** dla Natasha jest skojarzony ze wszystkimi osobami, z które pracuje Natasha. Pojedynczy rekord osoby **kontaktowej** dla Miguel jest skojarzony ze wszystkimi osobami, z które pracuje Miguel.

Te relacje są przechowywane w tabeli **Osoba kontaktowa dla strony**. Informacje te można znaleźć w formularzach, które są dostępne:

+ W formularzu **Konto** znajduje się karta o nazwie **Skojarzone kontakty**. Ta karta służy do skojarzenia jednego lub większej liczby kontaktów z wierszem **Konto**. W tym formularzu przypisujesz osobę kontaktową do organizacji. Po przypisaniu kontaktów można go wybrać jako główny kontakt dla tego konta. Za pomocą formularza **Szybkie tworzenie** można wybrać tylko osobę kontaktowa. Działanie jest takie same w przypadku korzystania z formularza **Dostawca** i gdy typem rekordu jest **Organizacja**.
+ Gdy znajdujesz się w formularzu **Kontakt** i wiersz jest wierszem odbiorca, dostawca lub oba (kontakt z paskami), pojawia się karta o nazwie **Skojarzone kontakty**. Ta karta służy do skojarzenia jednego lub większej liczby kontaktów. W tym formularzu przypisujesz osobę kontaktową dla klienta lub dostawcy B2C. Po przypisaniu kontaktów można go wybrać jako główny kontakt. Za pomocą formularza **Szybkie tworzenie** można wybrać tylko osobę kontaktowa.
+ Gdy znajdujesz się w formularzu **Kontakt**, a wiersz zawiera osobę kontaktową (kontakt bez pasków), znajduje się zakładka o nazwie **Skojarzone organizacje**. Użyj tej karty, aby powiązać jednego lub więcej klientów lub dostawców. W tym formularzu przypisujesz klienta lub dostawcę do podstawowej osoby kontaktowej. Odbiorca lub dostawca może być organizacją, osobą lub obiema organizacjami. W danym momencie można wybrać tylko jedną wartość z czterech pól.

    ![Karta Skojarzone organizacje](media/party-gab-image3.png)

    + Jeśli wybierzesz **Identyfikator strony**, kontakt źródłowy jest przypisany do wszystkich ról wybranej strony.
    + W przypadku wybrania opcji **Skojarzony kontakt** wybierany jest kontakt z listą, który jest typu „osoba”.
    + W przypadku wybrania opcji **Skojarzone konto** lub **Dostawca** wybierasz organizację.

    Niezależnie od wyborów, skojarzenie jest tworzone na poziomie jednostki i ma zastosowanie do wszystkich ról jednostki i jest przechowywane w jednostce „Kontakt dla strony”.

> [!Note]
> Nazwa wyświetlana tabeli **Osoba kontaktowa dla strony** w aplikacji dotyczącej relacji z klientem to **Kontakt dla odbiorcy/dostawcy**.

Po otwarciu wiersza **Osoba kontaktowa**, w którym **Jest odbiorcą** to **Nie** i **Jest dostawcą** to **Nie**, zobaczysz kartę **Skojarzone organizacje**. Użyj tej karty, aby skojarzyć z kontaktem jedną lub więcej organizacji odbiorcy lub dostawcy.

Po otwarciu wiersza **Osoba kontaktowa**, w którym **Jest odbiorcą** to **Tak** lub **Jest dostawcą** to **Tak**, zobaczysz kartę **Skojarzone kontakty**. Użyj tej karty, aby skojarzyć z kontaktem jedną lub więcej kontaktów.

## <a name="postal-address"></a>Adres pocztowy

Wprowadzono nową kartę o nazwie **Adresy** w formularzach **Konto**, **Kontakt** i **Dostawca**. Adresy obsługujące **adresy** N przy użyciu siatki, jak pokazano na tym obrazie:

![Siatka adresu pocztowego](media/party-gab-image4.png)

+ W kolumnie **Role adresu pocztowego** jest wymieniony cel adresu.
+ W kolumnie **Jest podstawowym** znajduje się lista adresów podstawowych.
+ W kolumnie **Numer adresu** jest wymieniona lista zamówień adresowych.
+ Przycisk **+ Nowy adres** umożliwia tworzenie nowego adresu. Można utworzyć dowolną liczbę adresów.

Pola **Adres 1** i **Adres 2** na karcie **Podsumowanie** formularza **Konto** odpowiadają odpowiednio adresom **Dostawy** i **Faktury**.

![Karta Podsumowanie dla adresu pocztowego](media/party-gab-image5.png)

Pola **Adres 1**, **Adres 2** i **Adres 3** na karcie **Podsumowanie** formularza **Kontakt** odpowiadają odpowiednio adresom **Biznesowemu**, **Dostawy** i **Faktury**.

## <a name="electronic-address"></a>Adres elektroniczny

Wprowadzono nową kartę o nazwie **Adresy elektroniczne** w formularzach **Konto**, **Kontakt** i **Dostawca**. Adresy obsługujące **adresy** N przy użyciu siatki, jak pokazano na tym obrazie:

![Siatka adresu elektonicznego](media/party-gab-image6.png)

+ W kolumnie **Typ** jest wymieniony typ adresu.
+ W kolumnie **Jest podstawowym** znajduje się lista adresów podstawowych.
+ W kolumnie **Cel** jest wymieniony cel adresu elektronicznego.
+ Przycisk **+ Nowy adres elektroniczny** umożliwia tworzenie nowego adresu. Można utworzyć dowolną liczbę adresów.

Adresy elektroniczne są dostępne tylko w tej siatce. W przyszłych wersjach wszystkie pola adresu elektronicznego i pocztowego zostaną usunięte z innych kart, na przykład karty **Podsumowanie** i **Szczegóły**.

## <a name="setup-instructions"></a>Instrukcje konfiguracji

Jeśli użytkownik jest już klientem systemu podwójnego zapisu, wymagane są następujące instrukcje konfiguracji. W przeciwnym razie można pominąć tę sekcję.

1. Zatrzymaj poniższe mapy, ponieważ nie są one już wymagane. Zamiast tego uruchom mapę Kontakty V2 (msdyn_contactforparties).

    + Kontakty CDS w wersji 2 i kontakty (odwołanie do kontaktów odbiorcy)
    + Kontakty CDS w wersji 2 i kontakty (odwołanie do kontaktów dostawcy)

2. Następujące mapowania jednostek są aktualizowane dla funkcji jednostki, więc do tych mapowań musi zostać zastosowana najnowsza wersja.

Mapa | Aktualizuj do tej wersji | Zmiany
---|---|---
Odbiorcy wersja 3 (konta) | 1.0.0.5 |Usunięto PartyNumber i inne pola powiązane z stroną, takie jak nazwa, dane osobowe, pola adresu pocztowego, pola elektronicznego adresu kontaktowego itp
Kontakty odbiorcy V3 (kontakty) | 1.0.0.5 | Usunięto PartyNumber i inne pola powiązane z stroną, takie jak nazwa, dane osobowe, pola adresu pocztowego, pola elektronicznego adresu kontaktowego itp
Dostawcy wersja 2 (msdyn_vendors) | 1.0.0.6 | Usunięto PartyNumber i inne pola powiązane z stroną, takie jak nazwa, dane osobowe, pola adresu pocztowego, pola elektronicznego adresu kontaktowego itp
Nagłówki ofert sprzedaży CDS (oferty) | 1.0.0.6 | Zamienił osobę kontaktowa na odwołanie ContactforParty.
Nagłówki faktur sprzedaży wer. 2 (faktury) | 1.0.0.4 | Zamienił osobę kontaktowa na odwołanie ContactforParty.
Nagłówki zamówień sprzedaży CDS (zamówienia sprzedaży) | 1.0.0.5 | Zamienił osobę kontaktowa na odwołanie ContactforParty.
Kontakty V2 (msdyn_contactforparties) | 1.0.0.2 | To jest nowa mapa. Jeśli masz poprzednią wersję rozwiązania strony, pamiętaj, aby zaktualizować tę mapę do najnowszej, jak już wymienionej.
Lokalizacje adresów pocztowych stron CDS (msdyn_partypostaladdresses) | 1.0.0.1  | To jest nowa mapa dodawana jako część wersji Preview poprzedniej strony.
Historia adresów pocztowych CDS w wersji 2 (msdyn_postaladdresses) | | To jest nowa mapa dodawana jako część wersji Preview poprzedniej strony.
Lokalizacje adresów pocztowych CDS (msdyn_postaladdresscollections) | | To jest nowa mapa dodawana jako część wersji Preview poprzedniej strony.
Kontakty strony V3 (msdyn_partyelectronicaddresses) | | To jest nowa mapa dodawana jako część wersji.

## <a name="templates"></a>Szablony

Zbiór map tabel współpracuje ze sobą na potrzeby interakcji między stronami i globalną książką adresową, jak pokazano w poniższej tabeli.

Aplikacja Finance and Operations | Aplikacja Customer Engagement     | opis
----------------------------|-----------------------------|------------
[Tytuły osoby kontaktowej](mapping-reference.md#223) | msdyn_salescontactpersontitles |
[Odbiorcy (wersja 3)](mapping-reference.md#101) | Konta |
[Odbiorcy (wersja 3)](mapping-reference.md#116) | kontakty |
[Strony usługi CDS](mapping-reference.md#220) | msdyn_parties |
[Lokalizacje adresu pocztowego strony usługi CDS](mapping-reference.md#233) | msdyn_partypostaladdresses |
[Historia adresu pocztowego usługi CDS V2](mapping-reference.md#235) | msdyn_postaladdresses |
[Lokalizacje adresu pocztowego usługi CDS](mapping-reference.md#234) | msdyn_postaladdresscollections |
[Nagłówek oferty sprzedaży CDS](mapping-reference.md#215) | Cytaty |
[Nagłówki zamówień sprzedaży CDS](mapping-reference.md#217) | salesorders |
[Formuły grzecznościowe](mapping-reference.md#222) | msdyn_complimentaryclosings |
[Kontakty wersja 2](mapping-reference.md#221) | msdyn_contactforparties |
[Role podejmujące decyzje](mapping-reference.md#224) | msdyn_decisionmakingroles |
[Funkcje stanowisk zatrudnienia](mapping-reference.md#225) | msdyn_employmentjobfunctions |
[Poziomy lojalności](mapping-reference.md#226) | msdyn_loyaltylevels |
[Osoby kontaktowe strony wer. 3](mapping-reference.md#236) | msdyn_partyelectronicaddresses |
[Typy osób](mapping-reference.md#227) | msdyn_personalcharactertypes |
[Nagłówki faktur sprzedaży wer. 2](mapping-reference.md#118) | faktury |
[Zwroty grzecznościowe](mapping-reference.md#228) | msdyn_salutations |
[Dostawcy wersja 2](mapping-reference.md#202) | msdyn_vendors |

Aby uzyskać więcej informacji, zobacz [Odniesienie do mapowania z podwójnym zapisem](mapping-reference.md).
