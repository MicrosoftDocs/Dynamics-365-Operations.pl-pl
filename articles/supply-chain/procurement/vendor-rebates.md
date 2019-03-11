---
title: Rabaty dostawcy
description: Ten temat zawiera omówienie najpopularniejszych zadań, które może wykonać podczas pracy z rabatami dostawcy. Rabaty dostawcy ułatwiają firmom zarządzanie programami rabatów dla dostawców dzięki automatyzacji zadań wymaganych do administrowania, śledzenia i wykorzystywania uzyskanych rabatów.
author: omulvad
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TAMVendRebateAgreement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 2012
ms.openlocfilehash: 90bee2925f135b3d626ba898a0e9995b5b8437ff
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "341081"
---
# <a name="vendor-rebates"></a>Rabaty dostawcy
[!include [banner](../includes/banner.md)]

Rabaty dostawcy ułatwiają firmom zarządzanie programami rabatów dla dostawców dzięki automatyzacji zadań wymaganych do administrowania, śledzenia i wykorzystywania uzyskanych rabatów.

Ten temat zawiera omówienie najpopularniejszych zadań, które może wykonać podczas pracy z rabatami dostawcy. Przegląd obejmuje następujące zadania:

- Przejrzenie szczegółów umowy rabatowej.
- Identyfikowanie zamówień uprawiających do skorzystania z rabatu i generowanie roszczeń dotyczących rabatu.
- Przejrzenie i zatwierdzanie roszczeń.

## <a name="audience-and-purpose"></a>Odbiorcy i cel

Informacje w tym temacie są przeznaczone dla osób podejmujących decyzje biznesowe w przedsiębiorstwach na stanowiskach takich jak menedżer ds. zaopatrzenia, dyrektor finansowy (CFO) i menedżer księgowości, których obowiązki są następujące:

- Negocjowanie cen dla dostawców, zniżek i umów rabatowych.
- Zarządzanie pracownikami, którzy przetwarzają roszczenia dotyczące rabatu i odbierają płatności.
- Zamawianie zapasów w najlepszych dostępnych cenach.

Osoby na tych stanowiskach szukają sposobów na osiągnięcie różnych celów. Oto kilka przykładów:

- Elastyczne dostosowanie do różnych typów programów promocji dla dostawców i warunków uzyskania rabatu.
- Zmniejszenie obciążeń administracyjnych i liczby błędów związanych z monitorowaniem realizacji promocji i przetwarzaniem roszczeń.
- Poprawa prognoz przepływów pieniężnych dzięki naliczeniu przyszłych należności.
- Określenie podstawy ilościowej dla trwających i przyszłych negocjacji z dostawcami na temat rabatów.

## <a name="review-details-of-a-vendor-rebate-agreement"></a>Przeglądanie szczegółów umowy rabatowej z dostawcą
Umowa rabatowa z dostawcą to zapis umowy z dostawcą, która określa wynegocjowane zasady i warunki, na jakich firma kwalifikuje się do korzyści pieniężnych w zamian za osiągnięcie wcześniej określonych celów dotyczących zakupów. Umowy rabatowe z dostawcą są zapisywane na stronie **Umowy rabatowe**.

Aby otworzyć stronę **Umowy rabatowe z dostawcą**, wybierz opcję **Zaopatrzenie i sourcing** &gt; **Rabaty dostawcy** &gt; **Umowy rabatowe**.

![Umowa zakupu](media/purchase-agreement.PNG)

Na stronie **Umowy rabatowe z dostawcą** można wyświetlić szczegóły dotyczące wynegocjowanych warunków umowy z dostawcą.

Nagłówek umowy warunki ogólne, które kwalifikują firmę do uzyskania rabatów. W efekcie informacje w nagłówku określają, że dostawca przyznaje rabat, po zakupie określonej ilości danego produktu. W nagłówku można także określić opcję jednostki miary rabatów i typ danych przy obliczeniach.

- Na karcie **Ogólne**, w polu **Opcja jednostki miary rabatów** można określić, czy jednostka miary powinna być warunkiem dla linii zamówienia zakupu kwalifikującym do roszczenia rabatu. 

    - **Konwertuj** — linia zamówienia zakupu uprawnia do rabatu dostawcy według umowy rabatowej. Otrzymasz rabat bez względu na jednostkę miary zastosowaną do linii.
    - **Dokładne dopasowanie** — aby kwalifikować się do rabatu, linia zakupów musi mieć tę samą jednostkę miary, jaką określono w umowie.

- Na kartce **Ogólne**, w polu **Typ daty przy obliczeniach** wybierz datę używaną do określenia, czy zakup występuje w okresie ważności rabatu.

    - **Utworzono** — użyj daty utworzenia zamówienia zakupu.
    - **Żądana dostawa** — użyj żądanej daty dostawy.

W wierszach umowy można bardziej szczegółowo określić umowę rabatową z dostawcą.

- W polu **Kumuluj zakupy według** można ustawić obliczanie roszczenia dotyczącego rabatu. Ilość można ustawić tak, aby zależała od okresu (tygodnia, miesiąca, roku, okresu istnienia lub okresu niestandardowego). Wartość **Faktura** oznacza. że roszczenie dotyczące rabatu będzie określane przy każdym fakturowaniu linii zamówienia zakupu.
- W polu **Na podstawie** można określić podstawę obliczania rabatu.

    - **Brutto** — rabat jest obliczany na podstawie ceny brutto pozycji.
    - **Netto** — rabat jest obliczany na podstawie ceny netto pozycji (czyli ceny po zastosowaniu innych zniżek).

- W polach **Konto naliczeń programu rabatowego** i **Konto wydatków programu rabatowego** znajdują się numery kont, na których kwoty naliczonego rabatu znajdą się podczas etapu pośredniego między zatwierdzeniem a przetworzeniem.
- Po ustawieniu opcji **Wymagane zatwierdzenie** na **Tak** roszczenie dotyczące rabatu musi zostać zatwierdzone przed naliczeniem i wypłaceniem.
- W polu **Typ podziału wiersza rabatu** określa podstawę dla rabatu.

    - **Ilość** — rabaty zależą od ilości.
    - **Kwota** — rabaty zależą od kwoty.

- Na skróconej karcie **Wiersze** można zobaczyć, w jaki sposób ustawić różne warstwy ilości w celu przyznania różnych rabatów. Przykładowo na poprzedniej ilustracji pola **Od wartości** i **Do wartości** wskazują, że ilość produktów od 10 do 19 sztuk będzie kwalifikować do rabatu 15 USD za sztukę.

    > [!NOTE]
    > Wartość **Od wartości** jest wliczana, a wartość **Do wartości** nie jest wliczana. Przykładowo pole **Typ podziału wiersza rabatu** jest ustawione na **Ilość** i wprowadzasz wartość **1** w polu **Od wartości**, a wartość **3** w polu **Do wartości**. W tym przypadku kwota rabatu ma zastosowanie po zakupie jednej lub dwóch pozycji, ale nie po zakupie trzech pozycji.

- W polu **Stan zatwierdzania w ramach przepływu pracy** wartość **Zatwierdzone** oznacza, że umowę można zastosować do zamówień zakupu, które spełniają warunki umowy.

## <a name="identify-orders-that-qualify-for-rebates-and-generate-rebate-claims"></a>Identyfikowanie zamówień uprawiających do skorzystania z rabatu i generowanie roszczeń dotyczących rabatu

Po złożeniu zamówień zakupu u dostawcy, z którym firma zawarła umowę rabatową program identyfikuje wszystkie przyszłe płatności kredytowe dostawcy. Jeżeli zamówienia zakupu kwalifikują się do rabatu, roszczenie dotyczące rabatu jest generowane dla każdego wiersza zamówienia zaraz po zaksięgowaniu faktury zakupu. Ten proces jest automatyczny. Później można przejrzeć oczekiwane rabaty i sprawdzić ich wpływ na koszt produktu i marżę zysku.

### <a name="view-details-of-rebates-that-are-applied-to-a-purchase-order-line-per-the-vendor-rebate-agreement"></a>Wyświetlanie szczegółów rabatów stosowanych do wiersza zamówienia zakupu zgodnie z umową rabatową z dostawcą
1. Na stronie **Zamówienie zakupu** wybierz wiersz zamówienia, a następnie wybierz opcję **Wiersz zamówienia zakupu** &gt; **Wyświetl** &gt; **Szczegóły ceny**.
2. Na stronie **Szczegóły ceny** wybierz skróconą kartę **Rabaty**.

Informacje o rabacie są także widoczne w polu **Rabat dostawcy** w sekcji **Szacowanie marży** strony **Szczegóły ceny**.

> [!NOTE]
> Na stronie **Parametry modułu Zaopatrzenie i sourcing**, na karcie **Ceny** sprawdź, czy opcja **Włączanie szczegółów ceny** jest ustawiona na **Tak**. Jeżeli opcja jest ustawiona na **Nie**, nie będzie można wyświetlić rabatów.

## <a name="review-and-approve-claims"></a>Przejrzenie i zatwierdzanie roszczeń
Generowane roszczenia dotyczące rabatu oznaczają przyszłe płatności, których należy oczekiwać od dostawcy. Przed wystawieniem noty kredytowej dla dostawcy właściciel umowy zwykle chce przejrzeć roszczenia i zatwierdzić je. Należy jednak pamiętać, że status roszczenia określa, czy roszczenie jest gotowe do przejścia procesu zatwierdzania.

### <a name="the-status-of-claims-and-the-effect-on-the-approval-process"></a>Stan roszczeń oraz wpływ na proces zatwierdzania
Po wygenerowaniu roszczenia jego stan jest ustawiany na **Do obliczenia**, jeżeli przyznany rabat jest skumulowany lub **Obliczony**, jeżeli rabat jest przyznawany według faktur. Jeżeli stan roszczenia to **Do obliczenia**, roszczenie musi przejść przez proces obliczania obsługiwany przez funkcję Kumuluj. Tylko roszczenia o stanie **Obliczone** mogą zostać uwzględnione w procesie zatwierdzania.

> [!NOTE]
> Jeżeli opcja **Wymagane zatwierdzenie** w umowie rabatowej z dostawcą jest ustawiona na **Nie**, wszystkie wygenerowane roszczenia będą miały stan **Zatwierdzone**. Zatwierdzenie jest obowiązkowe dla roszczeń skumulowanych.

### <a name="approve-claims-and-view-postings-and-invoice-details"></a>Zatwierdzanie roszczeń i wyświetlanie księgowań oraz szczegółów faktury
Po zatwierdzeniu roszczenia mogą zostać przetworzone przez moduł Rozrachunki z dostawcami. Nota kredytowa (faktura od dostawcy) na kwotę roszczenia dotyczącego rabatu jest generowana automatycznie. Kredyt może następnie zostać dodany do salda dostawcy, a zespół ds. rozrachunku z dostawcami może uwzględnić go w procesie zwykłego rozliczania.

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing** &gt; **Rabaty dostawcy** &gt; **Roszczenia dotyczące rabatu**, aby otworzyć roszczenie dotyczące rabatu.
2. Zamknij roszczenie dotyczące rabatu.
3. Oznacz roszczenie, a następnie w okienku akcji wybierz opcję **Zatwierdź**.
4. Na stronie żądania, w polu **Dostawca** wybierz dostawce, dla którego masz autoryzację do otrzymania rabatu, a następnie wybierz przycisk **OK**.

    Arkusz naliczania rabatów zostanie zaksięgowany dla kwoty roszczenia. To księgowanie obciąża rachunek Naliczone należności rabatów dostawcy na oczekiwany kredyt dostawcy i uznaje tymczasowy rachunek Naliczone odebrane rabaty dostawcy na oczekiwany zysk.

    ![Wiadomość](media/message.png)

5. Na liście rabatów wybierz wiersz, a następnie w okienku akcji wybierz opcję **Transakcje rabatowe**, aby wyświetlić i przejść do arkusza z numerem partii dla tego księgowania naliczania rabatu.

    Aby przenieść roszczenia do zwykłego procesu rozrachunku, pracownik ds. rozrachunków musi teraz dokończyć roszczenie dotyczące rabatu, uruchamiając funkcję Przetwarzaj.

6. W okienku akcji wybierz opcję **Przetwarzaj**, a następnie wybierz opcję **Filtruj**. W polu **Kryteria** dla pola **Konto dostawcy** wybierz dostawcę, dla którego chcesz przetworzyć roszczenia dotyczące rabatu, wybierz inne ważne filtry, a następnie wybierz przycisk **OK**.

    Paski komunikatów i zmiana stanu na **Zakończono** oznaczają wystąpienie następujących zdarzeń:

    - Księgowanie arkusza naliczania rabatów wycofało poprzednie kwoty tymczasowe na na rachunkach naliczania należności i wydatków.
    - Utworzona została faktura dostawcy (nota kredytowa) na kwotę rabatu.

        > [!NOTE]
        > Ustawienie opcji **Ręczne księgowanie faktury** na karcie **Program rabatowy** strony **Parametry modułu Zaopatrzenie i sourcing** określa, czy faktura dostawcy jest księgowana ręcznie, czy automatycznie w ramach przetwarzania roszczenia.

    - Po zaksięgowaniu faktury dostawcy, ręcznie lub automatycznie, konto należności dostawcy jest obciążane, a konto Otrzymane rabaty i odpisy jest uznawane.

        > [!NOTE] 
        > Numer konta Otrzymane rabaty i odpisy jest określone dla kategorii zaopatrzenia używanej w wierszu faktury zakupu dla rabatu. Z kolei kategoria zaopatrzenia jest ustawiana na karcie **Program rabatowy** strony **Parametry modułu Zaopatrzenie i sourcing**.

7. Na liście rabatów wybierz wiersz, a następnie w okienku akcji wybierz opcję **Transakcje rabatowe**, aby wyświetlić i przejść do arkusza z numerem partii dla tego księgowania naliczania rabatu, a także numeru faktury dostawcy.
8. Wybierz wiersz transakcji faktury dostawcy, a następnie w okienku akcji wybierz opcję **Faktura dostawcy**. Jeżeli faktura dostawcy została zaksięgowana zostanie wyświetlony arkusz faktur. W przeciwnym razie faktura dostawcy będzie widoczna jako oczekująca faktura dostawcy, która wymaga księgowania ręcznego.

    Wiersz faktury określa szczegóły faktury dostawcy dla kategorii zaopatrzenia **Prowizje i rabaty**.

9. Na stronie **Wszyscy dostawcy** wybierz dostawcę, od którego otrzymujesz rabat, a następnie w okienku akcji wybierz opcję **Transakcje**. Znajdź wiersz faktury. Kwota rabatu została dodana do salda dostawcy.

## <a name="summary"></a>Sumaryczny
Proces obsługi rabatów dostawcy obejmuje wiele zadań śledzenia ręcznego, których wykonanie jest często żmudne. Dzięki automatyzacji tych zadań funkcja zarządzania rabatem dostawcy ułatwia realizację następującego procesu:

- Generowanie prawidłowych roszczeń dotyczących rabatu
- Naliczenie oczekiwanych należności i tymczasowego zysku w księdze głównej
- Aktualizacja salda dostawcy i rachunku strat i zysków o należny odpis
