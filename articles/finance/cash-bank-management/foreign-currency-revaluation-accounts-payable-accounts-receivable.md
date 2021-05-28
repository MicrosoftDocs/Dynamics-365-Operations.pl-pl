---
title: Przeszacowanie w walucie dla rozrachunków z odbiorcami i rozrachunków z dostawcami
description: Ten temat zawiera informacje o procesie przeszacowania w walucie obcej, który jest wykonywany, aby zaktualizować wartość otwartych transakcji w modułach Rozrachunki z odbiorcami i Rozrachunki z dostawcami.
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustExchRateAdjustment, VendExchRateAdjustment
audience: Application User
ms.reviewer: roschlom
ms.custom: 14211
ms.assetid: defb1ea5-1f3e-4859-87d8-3f9954d3f388
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9d4e9a4bfdad4e69b13d7b0324f4978f13d6d295
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026164"
---
# <a name="currency-revaluation-for-accounts-payable-and-accounts-receivable"></a>Przeszacowanie w walucie dla rozrachunków z odbiorcami i rozrachunków z dostawcami

[!include [banner](../includes/banner.md)]

Wahania kursów wymiany powodują, że wartość teoretyczna (wartość księgowa) otwartych transakcji w walutach obcych zmienia się w czasie. Ten temat zawiera informacje o procesie przeszacowania w walucie obcej, który jest wykonywany, aby zaktualizować wartość otwartych transakcji w modułach Rozrachunki z odbiorcami i Rozrachunki z dostawcami. 

Wartość teoretyczna (wartość księgowa) otwartych transakcji w obcych walutach zmienia się w zależności od fluktuacji kursów wymiany. Aby zaktualizować wartość otwartych transakcji w module Rozrachunki z odbiorcami i Rozrachunki z dostawcami, uruchom proces przeszacowania w walucie obcej. Przeszacowanie w walucie obcej można wykonać zarówno dla rozrachunków z odbiorcami, jak i rozrachunków z dostawcami. Proces korzysta z nowego kursu wymiany do przeszacowywania otwartych kwot lub nierozliczonych kwot w określonym dniu. Różnica między kwotami zaksięgowanymi oryginalnie a kwotami przeszacowanymi spowoduje niezrealizowaną dodatnią lub ujemną różnicę kursową dla każdej otwartej transakcji. Księgi podrzędne rozrachunków z dostawcami i rozrachunków z odbiorcami są zaktualizowane tak, aby odzwierciedlały niezrealizowaną dodatnią lub ujemną różnicę kursową, a wpis zostaje zaksięgowany w księdze głównej.

## <a name="simulate-a-foreign-currency-revaluation"></a>Symulowanie przeszacowania w walucie obcej
Przed przeszacowywaniem kwoty w walucie obcej dla transakcji otwartych można uruchomić raport symulacji przeszacowania w walucie obcej dla tej samej daty i metody. Aby uruchomić raportu symulacji, na stronie **Przeszacowanie w walucie obcej** kliknij przycisk **Symulacja**. Raport umożliwia wyświetlenie podglądu kwoty niezrealizowanej dodatniej różnicy kursowej lub straty na podstawie parametrów określonych dla symulacji.

## <a name="process-a-foreign-currency-revaluation"></a>Przetwarzanie przeszacowania w walucie obcej
Strona **Przeszacowanie w walucie obcej** w obszarze **Zadania okresowe** służy do przeszacowywania otwartych transakcji. Można uruchomić proces w czasie rzeczywistym lub zaplanować uruchomienie przy użyciu zadania wsadowego. Podczas definiowania ustawień dla procesu przeszacowania należy określić, czy ma być drukowany raport wyników. Raport przeszacowania nie może być wydrukowany po zakończeniu procesu. W przypadku generowania raportu przeszacowania w walucie obcej w raporcie zostaną przedstawione różne salda na poziomie odbiorcy/dostawcy i waluty:

-   Sald odbiorców lub dostawców, którzy mają przeszacowane transakcje w walucie obcej. Widoczne są następujące salda:
    -   Oryginalne saldo w walucie obcej.
    -   Łączna kwota w walucie obcej w walucie księgowania na dzień poprzedniego przeszacowania.
    -   Łączna kwota w walucie obcej w walucie księgowania na dzień bieżącego przeszacowania.
    -   Różnica między poprzednim i obecnym przeszacowaniem. Różnica ta jest dodatkową niezrealizowaną dodatnią różnicą kursową lub stratą.
-   Suma niezrealizowanych dodatnich różnic kursowych lub strat dla każdej waluty.

Po każdym uruchomieniu przeszacowania w walucie obcej jest wprowadzany zapis. Z zapisu na stronie **Przeszacowanie w walucie obcej** wybierz opcję **Transakcje**, aby wyświetlić szczegółową listę transakcji, które zostały utworzone z powodu przeszacowania. Każda transakcja na załączniku reprezentuje otwarte transakcje, które zostały przeszacowane. Jeśli otwarta transakcja została przeszacowana więcej niż raz, zobaczysz dwa zapisy używające tego samego załącznika. Jeden zapis będzie dotyczył wycofania poprzedniej niezrealizowanej dodatniej lub ujemnej różnicy kursowej, a drugi nowej niezrealizowanej dodatniej lub ujemnej różnicy kursowej. Aby uruchomić proces przeszacowania, kliknij przycisk **Przeszacowanie w walucie obcej**. Zdefiniuj odpowiednie ustawienia następujących parametrów:

-   **Metoda** — metoda użyta w wybranym zadaniu przeszacowania w walucie obcej:
    -   **Norma** — oznacza, że zadania przeszacowania w walucie obcej są księgowane niezależnie od tego, czy powstaje zysk czy strata.
    -   **Minimum** — oznacza, że zadania przeszacowania w walucie obcej są księgowane tylko wtedy, gdy powstaje strata.
    -   **Data faktury** — oznacza, że zadania przeszacowania w walucie obcej używają oryginalnego kursu wymiany transakcji rewaloryzowanego na oryginalną walutę rozliczeniową. Wpływ wszelkich poprzednich przeszacowań w walucie obcej zostaje anulowany.
-   **Data rozważenia** — data, z którą w systemie znaleziono wszystkie transakcje zawierające otwarte (nierozliczone) kwoty. Kwoty w walucie obcej są ponownie przeszacowywane przy użyciu kursów wymiany, które są wprowadzane na stronie **Kursy wymiany walut** dla określonej daty. W przypadku przeszacowania kwoty w walucie obcej w danym dniu, data ta staje się ostatnią datą przeszacowania w walucie obcej dla korygowanych transakcji. Jeśli przeszacowanie w walucie obcej zostanie uruchomione z datą rozważenia wcześniejszą od daty ostatniego przeszacowania w walucie obcej dla już skorygowanych transakcji, zadanie okresowe nie skoryguje transakcji otwartych z wcześniejszą datą rozważenia i zawierających późniejszą datę ostatniego przeszacowania w walucie obcej.
-   **Data kursu** — data określająca kurs waluty używany w transakcji przeszacowania w walucie obcej.
-   **Użyj profilu księgowania z** — profil księgowania, który służy do wprowadzania domyślnego konta głównego dla rozrachunków z odbiorcami lub rozrachunków z dostawcami dla zapisów księgowych transakcji przeszacowania w walucie obcej:
    -   **Księgowanie** — używany jest profil księgowania transakcji odbiorcy.
    -   **Wybierz** — umożliwia wskazywanie profilu księgowania w polu **Profil księgowania**.
-   **Profil księgowania** — jeśli wybrano opcję **Wybierz** w polu **Użyj profilu księgowania z**, profil księgowania wprowadzony w tym polu określa profil transakcji przeszacowania w walucie obcej.
-   **Wymiary finansowe** — wymiary finansowe zaksięgowane we wpisach księgowych transakcji z przeszacowaniem w walucie obcej. Wymiary finansowe nie są sprawdzane pod względem reguł struktury konta. Struktura konta w chwili zaksięgowania faktur może nie być taka sama jak struktura kont obowiązująca w chwili ukończenia przesądu. W przypadku wybrania określonych wymiarów finansowych w procesie przesądu nie ma opcji, więc sprawdzanie poprawności struktury konta jest pomijane.  
    -   **Brak** — nie są księgowane żadne wymiary finansowe. Jeśli w strukturze konta wymagany jest wymiar finansowy, proces przeszacowania jest nadal aktywny i tworzy wpisy księgowe bez wymiarów finansowych. Otrzymasz najpierw wiadomość z ostrzeżeniem, co pozwala anulować przeszacowanie.
    -   **Tabela** — oznacza, że wymiary finansowe konta odbiorcy lub dostawcy zostały zaksięgowane w przypadku transakcji z przeszacowaniem w walucie obcej.
    -   **Zaksięgowanie** — oznacza, że wymiary finansowe przeszacowywanej transakcji zostały zaksięgowane w transakcjach z przeszacowaniem w walucie obcej. Domyślnie wymiary finansowe konta księgowego rozrachunków z dostawcami/rozrachunków z odbiorcami oryginalnych transakcji będą używane do ponownego przeszacowania konta głównego rozrachunków z dostawcami/rozrachunków z odbiorcami transakcji przeszacowania, a wymiary finansowe konta głównego wydatków/środków trwałych/zysków oryginalnej transakcji będą używane do konta głównego niezrealizowanej dodatniej różnicy kursowej/straty transakcji przeszacowania.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
