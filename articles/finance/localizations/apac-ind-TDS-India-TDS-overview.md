---
title: Omówienie podatku indyjskiego potrąconego w źródle (TDS)
description: Ten artykuł zawiera szczegółowe informacje na temat podatku indyjskiego potrąconego w źródle (TDS). Dokumentacja dokumentów TDS zawiera funkcje tej funkcji.
author: kailiang
ms.date: 03/19/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "15721"
- intro-internal
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 7ddcf11013921b5d5e242c9026d332d319ed8169
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896291"
---
# <a name="indian-tax-deducted-at-source-tds-overview"></a>Omówienie podatku indyjskiego potrąconego w źródle (TDS)

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera szczegółowe informacje na temat podatku indyjskiego potrąconego w źródle (TDS).

Dokumentacja dokumentów TDS zawiera funkcje tej funkcji. Wyjaśnia również, jak wykonać podstawową konfigurację TDS, obliczać TDS dla transakcji, zakończyć proces rozliczania TDS, rejestrować numery zaświadczeń TDS i generować zapytania TDS, wyciągi TDS i zaświadczenia TDS. Dokumentacja obejmuje następujące tematy:

- [Podstawowa konfiguracja TDS](apac-ind-TDS-TDS-ledger-accounts-setup.md)
- [Funkcjonalność projektanta formuł i limitu progowego używana do obliczania TDS](apac-ind-TDS-Formula-designer.md)
- [Obliczanie TDS dla faktur, płatności, skryptów dłużnych i transakcji międzyfirmowych](apac-ind-TDS-Calculate-TDS-on-invoices-using-journals.md)
- [Okresowy proces rozliczenia KDPW i rozliczenia kwoty KDPW na rzecz sprzedawców upoważnionych do uiszczania podatku dochodowego](apac-ind-TDS-Run-the-periodic-TDS-settlement-process.md)
- [Rejestracja i aktualizacja numerów i dat certyfikatów TDS](apac-ind-TDS-Record-TDS-concession-certificate-numbers.md)

## <a name="introduction-to-tds"></a>Wprowadzenie do TDS

Zgodnie z ustawą o podatku dochodowym z 1961 r., Podatek dochodowy jest potrącany u źródła przez odbiorcę usługi w momencie wpłaty zaliczki lub rozliczenia kredytu, w zależności od tego, co nastąpi wcześniej. Osoba dokonująca płatności musi odliczyć kwotę podatku i zapłacić dostawcy usługi jedynie saldo netto. TDS jest stosowany do usług określonych przez rząd, a podatek jest odliczany przy użyciu stawek określonych przez rząd na dany okres. Stawka potrącenia jest oparta na stanie jednostki, która otrzymuje płatność lub zapewnia usługę. Do stanów należą: **Osoba**, **Hindu Undivided Family** (**HUF**), **Spółka**, **Firma**, **Stowarzyszenie osób** (**Association of Persons - AOP**), **Grupa osób** (**Body of Individuals - BOI**) i **Władze lokalne**.

W poniższych sekcjach znajduje się lista usług, których według dokumentów TDS dotyczy rząd Indii.

**Mieszkańców**

- Dochód z wynagrodzenia (zgodnie z art. 192)
- Dochód z odsetek od papierów wartościowych (zgodnie z art. 193)
- Dochód z dywidendy (zgodnie z art. 194)
- Dochód z odsetek (zgodnie z art. 194A)
- Dochód na loteriach lub na loteriach (zgodnie z art. 194B)
- Wygranie z pul itp. (zgodnie z art. 194BB)
- Zleceniobiorcy i podwykonawcy (zgodnie z art. 194C)
- Prowizja ubezpieczeniowa (zgodnie z art. 194D)
- Dochód z depozytu w ramach krajowego programu oszczędnościowego (zgodnie z art. 194EE)
- Dochód z fundusz wspólnego inwestowania lub UTI (zgodnie z art. 194F)
- Prowizja, wynagrodzenie, nagroda itp. w przypadku sprzedaży lub loterii (zgodnie z art. 194G)
- Płatność prowizji lub opłaty brokerskie (zgodnie z art. 194H)
- Wynajem (zgodnie z art. 194I)
- Serwis zawodowy (zgodnie z art. 194J)
- Dochód z jednostek (zgodnie z art. 194K)
- Płatność kompensacie w momencie nabycia pewnego majątku (zgodnie z art. 194LA)

**Nierezydenci**

- Płatności dla organizacji sportowej lub sportowej nierezydentów (zgodnie z art. 194E)
- Inne sumy (zgodnie z art. 195)
- Dochody w odniesieniu do jednostek nierezydentów (zgodnie z art. 196A)

    - Dochód z obligacji w walucie obcej lub akcji spółki indyjskiej (zgodnie z art. 196C)
    - Dochody zagranicznych inwestorów instytucjonalnych z tytułu papierów wartościowych (zgodnie z art. 196D)
    - Wynagrodzenie i wszystkie inne dodatnie dochody w ramach dowolnego dochodu (sekcja 192)
    - Odsetki od papierów wartościowych (zgodnie z art. 193)
    - Odsetki inne niż odsetki od papierów wartościowych (zgodnie z art. 194A)
    - Płatności na rzecz wykonawców i podwykonawców (zgodnie z art. 194C)
    - Wygrane na loteriach lub w krzyżykach (zgodnie z art. 194B)
    - Wygrane z wyścigów konnych (zgodnie z art. 194BB)
    - Komisja ubezpieczeniowa pokrywająca wszystkie płatności związane z zakupem działalności ubezpieczeniowej (zgodnie z art. 194D)
    - Wszelkie odsetki inne niż odsetki od papierów wartościowych należne nierezydentom niebędącym spółką lub spółce zagranicznej (zgodnie z art. 195)
    - Wypłata dla sportowca niebędącego rezydentem, w tym sportowca lub stowarzyszenia lub instytucji sportowej. W przypadku sportowca niebędącego rezydentem, płatności z tytułu reklam i artykułów dotyczących dowolnej gry / sportu w Indiach w gazetach, magazynach itp. hest włączony (zgodnie z art. 194E)
    - Płatność z tytułu depozytów w ramach NSS \[krajowego programu oszczędnościowego\] (zgodnie z art. 194EE)
    - Płatność na konto ponownego wykupu jednostek według funduszu wspólnego inwestowania lub UTI (zgodnie z art. 194F)
    - Płatność prowizji lub opłaty brokerskie (zgodnie z art. 194H)
    - Zapłata za wynajem (sekcja 194I)
    - Zapłata za usługi techniczne i zawodowe (sekcja 194J)
    - Prowizja dla magazynu, dystrybutorów, kupców i sprzedających biletów na loterię, w tym kupony (sekcja 194G)
    - Przychód z jednostek nabytych w walucie obcej lub długoterminowych zyskach z kapitału powstałych w wyniku przeniesienia takich jednostek nabytych w walucie obcej (sekcja 196B)
    - Płatność wszelkich dochodów niemówiąca rezydentów z tytułu odsetek lub dywidend od obligacji i akcji (sekcja 196C)

Identyfikatory TDS są obliczane dla transakcji zakupu, sprzedaży, zwrotów sprzedaży, not korygjących, nabyć środków trwałych, przedpłat, płatności zaliczek, skryptów dłużnych, podatku od pracy i transakcji międzyfirmowych.

> [!NOTE]
> W obecnym indyjskim scenariuszu podatku TDS nie jest obliczany na podstawie transakcji sprzedaży. Jednak system zawiera także przepisy służące do obliczania TDS, które mogą być odzyskane w przypadku transakcji sprzedaży, w szczególności w przypadku transakcji międzyfirmowych.

W obliczeniu TDS zawsze jest uwzględniany próg i próg wyjątków, które są zdefiniowane dla składnika TDS.

Należy uruchomić okresowy proces rozliczenia podatku potrącanego u źródła, a płatności podatku potrącanego u źródła muszą zostać rozliczone na rzecz dostawców urzędu podatku potrącanego u źródła.

Numery i daty certyfikatów TDS otrzymanych od dostawców lub odbiorców mogą być rejestrowane i aktualizowane. Dodatkowo wyciągi kwartalne na formularzu 26Q i formularzu 27Q oraz zaświadczenie na formularzu 16A dla TDS można wygenerować w Finance.

## <a name="setting-up-and-working-with-tds"></a>Konfigurowanie i praca z TDS

Oto przegląd procesu konfiguracji i pracy z TDS:

1. **Konfiguracja TDS:**

    - Konfigurowanie parametrów:

        - W parametrach księgi głównej aktywuj parametry związane z TDS.
        - W parametrach księgi głównej skonfiguruj sekwencję numerów dla płatności potrąconej zaliczki na podatek.
        - Konfigurowanie parametrów podatku TDS w modułach Rozrachunki z dostawcami i Rozrachunki z odbiorcami.

    - Konfiguracja podstawowa:

        - Skonfiguruj numery rejestracji TDS firmy, odbiorców i dostawców.
        - Skonfiguruj grupy składników TDS.
        - Skonfiguruj składniki TDS, dołącz do nich grupy składników TDS oraz zdefiniuj dla nich próg i próg wyjątków.
        - Ustawianie urzędów TDS.
        - Ustaw okresy rozliczeniowe TDS.
        - Skonfiguruj kody podatków TDS i dołącz do nich składniki TDS.
        - Skonfiguruj grupy podatkowe TDS i dołącz do nich kody podatków TDS.
        - W projektancie formuły zdefiniuj formułę, aby obliczyć TDS dla grupy TDS.
        - Rejestrowanie numerów certyfikatów koncesji TDS.

    - Konta księgowe i ustawienia firmy:

        - Skonfiguruj konta zobowiązań i należności TDS.
        - Skonfiguruj odliczenie podatku i numer konta windykacyjnego (TAN) oraz kategorię typu odliczenia dla firmy.

    - Inne ustawienia:

        - Skonfiguruj harmonogram płatności, który zawiera alokację TDS.
        - Skonfiguruj rodzaj opłaty za płatności na rzecz organu TDS.
        - Skonfiguruj informacje o grupach TDS, stałych numerach kont (PAN) i TAN dla dostawców i klientów.

2. **Obliczanie TDS w transakcjach**

    - Faktury i płatności
    - Skrypty dłużne
    - Zaliczki
    - Zaliczki

3. **Rozliczenie TDS**

    - Okresowy proces rozliczania TDS
    - Rozliczenie płatności podatku potrącanego u źródła na rzecz dostawców urzędu podatku potrąconego u źródła i wygenerowanie dokumentu informacyjnego TDS

4. **Zapytania, wyciągi i certyfikaty TDS:**

    - Rejestruj i aktualizuj numery i daty certyfikatów TDS.
    - Wygeneruj zapytanie dotyczące TDS i zaksięgowanego zapytania TDS.
    - Generowanie formularzy 27A, formularzy 26Q i formularzy 27Q TDS oraz kwartalnych wyciągów e-TDS.
    - Wygeneruj certyfikat TDS na formularzu 16A.
