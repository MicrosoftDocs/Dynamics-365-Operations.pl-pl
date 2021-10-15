---
title: Raport kosztów z wyładunkiem
description: W tym temacie opisano sposób wyszukiwania i używania różnych typów raportów dostępnych w module Koszty z wyładunkiem.
author: sherry-zheng
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-21
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: cb0ea44c0924fc5d2c295a9285701d1f678c3473
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571744"
---
# <a name="landed-cost-reports"></a>Raport kosztów z wyładunkiem

[!include [banner](../../includes/banner.md)]

## <a name="outstanding-invoices"></a>Zaległe faktury

Raport zaległych faktur zawiera listę wszystkich nieuregulowanych faktur na różnych poziomach kosztów skojarzonych z każdą podróżą. Służy do regularnego uzgadniania kosztów podróży i podróży z listą transakcji finansowych. Po zafakturowaniu kosztu narzutów jest on usuwany z raportu.

Aby wygenerować raport o zaległych fakturach, wykonaj następujące kroki.

1. Przejdź do raportu **Koszty z wyładowaniem \> Raporty \> Śledzenie \> Zaległe faktury**.
1. W oknie dialogowym **Zaległe faktury** w polu **Na dzień** określ datę. Każda faktura, która była zaległa w dniu tego dnia lub wcześniej, zostanie uwzględniona w wynikach.
1. W obszarze **Pokaż** wybierz jedną z następujących opcji:

    - **Koszt niefakturowany** — uwzględnia koszty zafakturowane wysyłki, które mają oszacowaną wartość kosztową, ale nie koszt rzeczywisty.
    - **Zapasy nie zostały zafakturowane** — uwzględnij koszty, które zostały zafakturowane, ale nie otrzymano jeszcze zamówienia zakupu.
    - **Wszystkie nie zafakturowane** — uwzględnij wyniki opcji **Koszt nie zafakturowany** i opcji **Zapasy niefakturowane**.

1. Ustaw opcję **Uwzględnij nowe koszty** na wartość *Tak*, aby uwzględnić koszty, dla których nie został jeszcze koszt rzeczywisty, a zapasy nie zostały odebrane. Jeśli zostanie ustawiona wartość *Nie*, raport będzie zawierał tylko koszty, które zostały zafakturowane.
1. W sekcji **Widok** włącz każdy typ szczegółów, które chcesz uwzględnić w raporcie.
1. Jak w przypadku raportów innych typów w firmie Microsoft Dynamics 365 Supply Chain Management, użyj skróconej karty **Miejsce docelowe**, aby wybrać format wyjściowy raportu.
1. Tak jak w przypadku raportów innych typów w Supply Chain Management, użyj skróconej karty **Rekordy do uwzględnienia**, aby jeszcze bardziej ograniczyć liczbę rekordów, które zostaną uwzględnione w raporcie.
1. Kliknij przycisk **OK**. Raport zostanie wygenerowany.

## <a name="activityprovider-analysis-reports"></a>Raporty z analizy działalności / dostawcy

Raporty analizy działań/dostawców pozwalają sprawdzić poprawność szacunków czasu poszczególnych dostawców.

Aby wygenerować raport analizy aktywności / dostawcy, wykonaj następujące kroki.

1. W zależności od typu raportu, który chcesz utworzyć, wykonaj jedną z poniższych czynności:

    - Przejdź do **Koszt z wyładunkiem \> Raporty \> Analiza działalności / usługodawcy według działalności**. W takim przypadku szacowania czasu zostaną pogrupowane według działań.
    - Przejdź do **Koszt z wyładunkiem \> Raporty \> Analiza działalności / dostawcy według dostawcy**. W takim przypadku szacowania czasu zostaną pogrupowane według dostawcy.

    Zostanie wyświetlone okno dialogowe **Analiza działań/dostawców według działań** lub **Analiza działań/dostawców według dostawców**. Obie opcje są dostępne w obu oknach dialogowych.

1. Jak w przypadku raportów innych typów w Supply Chain Management , użyj skróconej karty **Miejsce docelowe**, aby wybrać format wyjściowy raportu.
1. Tak jak w przypadku raportów innych typów w Supply Chain Management, użyj skróconej karty **Rekordy do uwzględnienia**, aby jeszcze bardziej ograniczyć liczbę rekordów, które zostaną uwzględnione w raporcie.
1. Kliknij przycisk **OK**. Raport zostanie wygenerowany.

## <a name="voyage-costing-reports"></a>Raporty wyceny podróży

Raporty kosztów podróży przedstawiają koszt towarów i koszty importu na folio, kontener wysyłkowy lub podróż, w zależności od opcji wybranych podczas generowania raportu. Każdy raport dotyczący kosztów podróży umożliwia przeglądanie szacunkowych kosztów podróży w porównaniu z kosztami rzeczywistymi i można je podzielić według kilku czynników identyfikujących.

Aby wygenerować raport kosztów podróży, wykonaj następujące kroki.

1. W zależności od typu raportu, który chcesz utworzyć, wykonaj jedną z poniższych czynności:

    - Przejdź do **Koszt z wyładunkiem \> Raporty \> Wycena \> Koszt podróży według kosztów indywidualnych**. W takim przypadku indywidualna opcja kosztu pokaże koszty importu według obszaru kosztów na kod rodzaju kosztu.
    - Przejdź do **Koszt z wyładunkiem \> Raporty \> Wycena \> Koszt podróży według kategorii raportowania**. W takim przypadku koszt importu zostanie rozbity na różne kategorie raportowania. Typy kosztów są pogrupowane według kategorii raportowania.

    Zostanie wyświetlone okno dialogowe **Wycena podróży według poszczególnych kosztów** lub okno dialogowe **Wycena podróży według kategorii raportowania**. Te okna dialogowe są podobne. Wszelkie różnice zostały odnotowane w pozostałej części tej procedury.

1. Jeśli zostanie otwarte okno dialogowe **Wycena podróży za pomocą kategorii raportowania**, w polu **Koszt** wybierz jedną z następujących wartości:

    - **Wartość kosztu** — wartość jest obliczana przy użyciu kosztów automatycznych lub tworzona ręcznie w obszarze kosztów.
    - **Oszacowane** — po otrzymaniu towarów jest ustawiany szacowany koszt.
    - **Rzeczywiste** — Po zafakturowaniu zamówienia koszt rzeczywisty jest ustalany na podstawie kosztu na fakturze.
    - **Najlepsze** — system użyje opcji, które z trzech poprzednich opcji są najdokładniejsze. (Zalecamy wybranie tej opcji).

1. Ustaw wartość **Tak** dla opcji *Na pozycję*, aby wyświetlić koszt każdego towaru. Ustaw dla niego wartość *Nie*, aby pokazać koszty na podróż.
1. W sekcji **Widok** wybierz kategorie, według których ma być rozbicie kosztów.
1. W sekcji **Wymiary** wybierz wymiary, które mają być dołączane do raportu.
1. Jak w przypadku raportów innych typów w Supply Chain Management , użyj skróconej karty **Miejsce docelowe**, aby wybrać format wyjściowy raportu.
1. Tak jak w przypadku raportów innych typów w Supply Chain Management, użyj skróconej karty **Rekordy do uwzględnienia**, aby jeszcze bardziej ograniczyć liczbę rekordów, które zostaną uwzględnione w raporcie.
1. Kliknij przycisk **OK**. Raport zostanie wygenerowany.

## <a name="shipping-container-receipts-list"></a>Lista przyjęć kontenera wysyłkowego

Lista przychodów kontenerów wysyłkowych zawiera wszystkie nieuznane ilości, które są należne w oczekiwanym dniu lub wcześniej. Pracownicy magazynu mogą używać tego raportu do identyfikowania oczekiwanych towarów w kontenerze wysyłkowym. Można go również używać do ręcznego sprawdzania poprawności towarów odbieranych w kontenerze wysyłkowym.

Aby wygenerować listę przychodu kontenera wysyłkowego, wykonaj następujące kroki.

1. Przejdź do **Koszt z wyładunkiem \> Raporty \> Śledzenie \> Lista przyjęć kontenerów transportowych**.
1. W oknie dialogowym **Lista przyjęć kontenerów transportowych** w polu **Oczekiwana data** określ datę. Wszelkie ilości, które nie zostały odebrane w tym dniu lub wcześniej, zostaną uwzględnione w danych wyjściowych.
1. W sekcji **Wymiary** wybierz wymiary, które mają być dołączane do raportu.
1. Jak w przypadku raportów innych typów w Supply Chain Management , użyj skróconej karty **Miejsce docelowe**, aby wybrać format wyjściowy raportu.
1. Tak jak w przypadku raportów innych typów w Supply Chain Management, użyj skróconej karty **Rekordy do uwzględnienia**, aby jeszcze bardziej ograniczyć liczbę rekordów, które zostaną uwzględnione w raporcie.
1. Kliknij przycisk **OK**. Raport zostanie wygenerowany.

## <a name="expected-delivery-report"></a>Raport oczekiwanej dostawy

Raport o oczekiwanej dostawie zawiera podstawowe informacje o podróży, pojemniku transportowym, folio, pozycjach i spodziewanej dacie dostawy.

Aby wygenerować oczekiwany raport dostarczenia, wykonaj następujące kroki.

1. Przejdź do raportu **Koszty z wyładowaniem \> Raporty \> Śledzenie \> Oczekiwana dostawa**.
1. W oknie dialogowym **Oczekiwana dostawa** w polu **Oczekiwana data** wybierz datę, od kiedy oczekiwana jest dostawa towarów do magazynu docelowego. Każdy wiersz podróży, który ma oczekiwaną datę w lub wcześniejszą, a który nie został jeszcze odebrany, będzie uwzględniony w wynikach.
1. Opcjonalnie: W polu **Konto dostawcy** wybierz konto dostawcy, aby uwzględnić tylko dostawy od określonego dostawcy.
1. W sekcji **Wymiary** wybierz wymiary, które mają być dołączane do raportu.
1. Jak w przypadku raportów innych typów w Supply Chain Management , użyj skróconej karty **Miejsce docelowe**, aby wybrać format wyjściowy raportu.
1. Tak jak w przypadku raportów innych typów w Supply Chain Management, użyj skróconej karty **Rekordy do uwzględnienia**, aby jeszcze bardziej ograniczyć liczbę rekordów, które zostaną uwzględnione w raporcie.
1. Kliknij przycisk **OK**. Raport zostanie wygenerowany.
