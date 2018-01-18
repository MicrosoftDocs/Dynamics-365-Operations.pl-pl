---
title: "Zarządzanie zmianami i szufladami kasowymi"
description: "W tym artykule wyjaśniono, jak skonfigurować i używać dwóch typów zmian w punkcie sprzedaży detalicznej (POS) — wspólnych i autonomicznych. Zmiany wspólne mogą być wykorzystywane przez wielu użytkowników w wielu miejscach, podczas gdy zmiany autonomiczne mogą być używane tylko przez jednego pracownika na raz."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailHardwareProfile, RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 105011
ms.assetid: 49a0fcc9-d4db-45ad-8c4b-213ccaced82b
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b8e12f3f4c2f8f5a596c8994f2a4571d8a907062
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="shift-and-cash-drawer-management"></a>Zarządzanie zmianami i szufladami kasowymi

[!include[banner](includes/banner.md)]


W tym artykule wyjaśniono, jak skonfigurować i używać dwóch typów zmian w punkcie sprzedaży detalicznej (POS) — wspólnych i autonomicznych. Zmiany wspólne mogą być wykorzystywane przez wielu użytkowników w wielu miejscach, podczas gdy zmiany autonomiczne mogą być używane tylko przez jednego pracownika na raz.

Istnieją dwa typy zmian stosowanych w punktach sprzedaży detalicznej (POS): autonomiczne i wspólne. Zmiany autonomiczne mogą być wykorzystywane tylko przez jednego pracownika na raz. Zmiany wspólne mogą być wykorzystywane przez wielu użytkowników w wielu miejscach. W związku z tym w praktyce są używane do tworzenia pojedynczych zmian dla wielu pracowników w sklepie.

## <a name="standalone-shifts"></a>Zmiany autonomiczne
Zmiany autonomiczne są używane w tradycyjnych scenariuszach stacjonarnych punktów sprzedaży, gdzie gotówka jest uzgadniana niezależnie w każdej kasie POS. Na przykład w środowisku sklepu spożywczego zazwyczaj istnieje kilka stacjonarnych kas i do każdej jest przypisany kasjer. W takim przypadku każda kasa prawdopodobnie wykorzystuje zmianę autonomiczną, a kasjer jest odpowiedzialny za kasę rejestrującą lub fizyczne środki pieniężne w tej kasie. Autonomiczna zmiana obejmuje wszystkie działania w tej kasie podczas zmiany kasjera. Z kolei działania mogą obejmować wprowadzenie kwoty otwarcia do kasy rejestrującej, wszystkie czynności usuwania i dodawania gotówki poprzez operacje takie jak przekazanie pieniędzy do banku czy przyjęcie do kasy oraz deklarowanie stanu kasy (środków płatniczych) na koniec zmiany.

### <a name="set-up-a-stand-alone-shift"></a>Konfigurowanie zmiany autonomicznej

Zmianę autonomiczną wyznacza się na poziomie szuflady kasowej. Poniższa procedura przedstawia sposób konfigurowania autonomicznej zmiany w kasie w punkcie sprzedaży.

1.  Kliknij kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Profile punktów sprzedaży** &gt; **Profile sprzętu**.
2.  Wybierz profil sprzętu, który ma być używany dla autonomicznej zmiany.
3.  Na skróconej karcie **Szuflada** upewnij się, że w opcji **Wspólna szuflada dla zmiany** zaznaczono wartość **Nie**.
4.  Kliknij przycisk **Zapisz**.
5.  Kliknij kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Rejestry**.
6.  Zaznacz kasę, która wymaga autonomicznej zmiany, i kliknij przycisk **Edytuj**.
7.  W polu **Profil sprzętu** zaznacz profil sprzętu, który został wybrany w kroku 2.
8.  Kliknij przycisk **Zapisz**.
9.  Kliknij kolejno opcje **Handel detaliczny** &gt; **Dane IT sieci sprzedaży** &gt; **Harmonogram dystrybucji**.
10. Wybierz harmonogram dystrybucji **1090**, a następnie kliknij przycisk **Uruchom teraz**, aby zsynchronizować zmiany z punktem sprzedaży.

### <a name="use-a-stand-alone-shift"></a>Używanie zmiany autonomicznej

1.  Zaloguj się w kasie POS.
2.  Jeśli nie jest otwarta żadna zmiana, wybierz opcję **Otwórz nową zmianę**.
3.  Przejdź do operacji **Zadeklaruj kwotę początkową** i określ ilość gotówki, która zostanie dodana do kasy rejestrującej na początek dnia pracy.
4.  Wykonaj kilka transakcji.
5.  Na koniec dnia wybierz opcję **Deklaracja metody płatności**, aby zadeklarować kwotę gotówki pozostającą w szufladzie kasowej.
6.  Wprowadź ilość gotówki i kliknij przycisk **Zapisz**, aby zapisać deklarację środków płatniczych.
7.  Wybierz opcję **Zamknij zmianę**, aby zamknąć zmianę.

**Uwaga:** Podczas zmiany są też dostępne inne operacje, w zależności od procesów biznesowych stosowanych na miejscu. Za pomocą operacji **Przekazanie pieniędzy do sejfu**, **Przekazanie pieniędzy do banku** i **Pobranie środków płatniczych** można usunąć pieniądze z kasy rejestrującej w ciągu dnia lub przed zamknięciem zmiany. Jeśli w kasie rejestrującej skończy się gotówka, można użyć operacji **Przyjęcie do kasy**, aby dodać gotówkę do szuflady.

## <a name="shared-shifts"></a>Zmiany wspólne
Zmiany wspólne są wykorzystywane w środowisku, gdzie wielu kasjerów współużytkuje szufladę kasową lub zestaw szuflad kasowych przez cały dzień pracy. Zazwyczaj wspólne zmiany stosuje się w mobilnych punktach sprzedaży. W takim środowisku kasjerzy nie są przypisywani jako osoby odpowiedzialne za konkretne kasy. Zamiast tego wszyscy kasjerzy muszą mieć możliwość realizowania sprzedaży i dodawania gotówki do najbliższej szuflady kasowej. W tym scenariuszu szuflady kasowe współużytkowane przez wszystkich kasjerów należą do wspólnej zmiany. Wszystkie szuflady kasowe we wspólnej zmianie należą do tej samej zmiany na potrzeby wykonywania działań związanych z zarządzaniem gotówką podczas tej zmiany. W związku z tym kwota początkowa zmiany powinna być sumą wszystkich środków pieniężnych we wszystkich szufladach kasowych należących do wspólnej zmiany. Analogicznie deklaracja środków płatniczych będzie sumą wszystkich środków pieniężnych we wszystkich szufladach kasowych należących do wspólnej zmiany. **Uwaga:** W każdym sklepie może być otwarta jednocześnie tylko jedna wspólna zmiana. W tym samym sklepie można używać zmian wspólnych i autonomicznych.

### <a name="set-up-a-shared-shift"></a>Konfigurowanie zmiany wspólnej

1.  Kliknij kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Profile punktów sprzedaży** &gt; **Profile sprzętu**.
2.  Wybierz profil sprzętu, który ma być używany dla wspólnej zmiany.
3.  Na skróconej karcie **Szuflada** w opcji **Wspólna szuflada dla zmiany** ustaw wartość **Tak**.
4.  Kliknij przycisk **Zapisz**.
5.  Kliknij kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Rejestry**.
6.  Zaznacz kasę, która wymaga wspólnej zmiany, i kliknij przycisk **Edytuj**.
7.  W polu **Profil sprzętu** zaznacz profil sprzętu, który został wybrany w kroku 2.
8.  Kliknij przycisk **Zapisz**.
9.  Kliknij kolejno opcje **Handel detaliczny** &gt; **Dane IT sieci sprzedaży** &gt; **Harmonogram dystrybucji**.
10. Wybierz harmonogram dystrybucji **1090**, a następnie kliknij przycisk **Uruchom teraz**, aby zsynchronizować zmiany z punktem sprzedaży.

### <a name="use-a-shared-shift"></a>Używanie zmiany wspólnej

1.  Zaloguj się w kasie POS.
2.  Jeśli kasa POS nie jest jeszcze podłączona do stacji sprzętowej, zaznacz opcję **Operacja bez szuflady**, a następnie wybierz operację **Wybierz stację sprzętową**, aby uaktywnić stację sprzętową dla wspólnej zmiany. Ten krok jest wymagany tylko podczas dodawania kasy po raz pierwszy do środowiska wspólnej zmiany.
3.  Wyloguj się z kasy POS, a następnie ponownie zaloguj.
4.  Kliknij opcję **Utwórz nową zmianę**.
5.  Kliknij opcję **Zadeklaruj kwotę początkową**.
6.  Wprowadź kwotę początkową dla wszystkich szuflad kasowych w sklepie, które należą do wspólnej zmiany, a następnie kliknij przycisk **Zapisz**.
    -   Aby dodać część kwoty początkowej do każdej kolejnej szuflady kasowej, użyj operacji **Wybierz stację sprzętową** w celu uaktywnienia stacji sprzętowej.
    -   Aby dodać kasę rejestrującą do konkretnej szuflady kasowej, użyj operacji **Otwarta szuflada**.
    -   Kontynuuj, aż wszystkie szuflady kasowe we wspólnej zmianie będą miały swój udział w kwocie początkowej.

7.  Na koniec dnia otwórz każdą szufladę kasową i wyjmij gotówkę.
8.  Po usunięciu gotówki z ostatniej szuflady kasowej policz wszystkie środki pieniężne ze wszystkich szuflad.
9.  Użyj operacji **Deklaracja metody płatności**, aby zadeklarować łączną kwotę gotówki ze wszystkich szuflad kasowych uwzględnionych we wspólnej zmianie.
10. Użyj operacji **Zamknij zmianę**, aby zamknąć wspólną zmianę.





