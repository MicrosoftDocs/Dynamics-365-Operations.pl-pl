---
title: Bank — przeszacowanie w walucie obcej
description: Ten artykuł zawiera omówienie procesu bankowego przeszacowania w walucie obcej. Zawiera informacje dotyczące programu instalacyjnego, procesu, obliczenia dla procesu i wycofywania transakcji przeszacowania.
author: angelad116
ms.date: 12/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankCurrencyRevalHistory
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2019-03-08
ms.dyn365.ops.version: 10
ms.openlocfilehash: 2d5e8a36d3b4d44c9ad0454db94164adebf80997
ms.sourcegitcommit: 69d7dd6a2d0dc7f2661c7d1f61e8874c7bde1448
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2022
ms.locfileid: "9887268"
---
# <a name="bank-foreign-currency-revaluation"></a>Bank — przeszacowanie w walucie obcej

[!include [banner](../includes/banner.md)]


Ten artykuł zawiera omówienie procesu bankowego przeszacowania w walucie obcej. Wyjaśnia, jak ustawić i uruchomić proces i zawiera informacje o obliczeniach dla procesu. Ponadto wyjaśniono, jak wycofać transakcje przeszacowania, gdy jest wymagane wycofanie.

Konwencje księgowe wymagają, aby podczas zamknięcia okresu salda kont banku w walutach obcych zostały przeszacowane przy użyciu różnych typów kursów wymiany (bieżących, historycznych, średnich itp.). Bankowe przeszacowanie w walucie obcej może służyć do przeszacowywania jednego lub więcej kont bankowych. Ta funkcja jest także dostępna globalnie. W związku z tym na jednej stronie można przeszacować rachunki bankowe wszystkich podmiotów prawnych, do których masz dostęp.

> [!NOTE]
> Podczas wykonywania procesu przeszacowania następuje przeszacowanie salda każdego konta bankowego zaksięgowanego w walucie obcej. Transakcje niezrealizowanych dodatnich lub ujemnych różnic kursowych, które są tworzone podczas procesu przeszacowania, są generowane przez system. W razie potrzeby mogą być tworzone dwie transakcje: jedna dla waluty rozliczeniowej i druga dla waluty raportowania, jeśli dotyczy. Każdy zapis księgowy zostanie zaksięgowany jako niezrealizowana dodatnia lub ujemna różnica kursowa i dodatkowo na przeszacowywanym koncie głównym.

## <a name="prepare-to-run-foreign-currency-revaluation"></a>Przygotowanie do wykonania przeszacowania w walucie obcej

Przed uruchomieniem procesu przeszacowania potrzebne jest wykonanie następującej konfiguracji.

- Na stronie **Księga** określ typ kursu wymiany. Jeśli typ kursu wymiany nie jest określony na koncie głównym, ten typ kursu wymiany będzie używany podczas przeszacowywania w walucie obcej.
- Na stronie **Księga** określ konta zrealizowanej dodatnią różnicę kursową, zrealizowanej ujemną różnicę kursową oraz niezrealizowanej różnicy kursowej dla przeszacowania waluty. Zrealizowana dodatnia różnica kursowa i zrealizowana ujemna różnica kursowa kont są używane podczas transakcji rozrachunków z dostawcami i rozrachunków z odbiorcami. Niezrealizowana dodatnia różnica kursowa i niezrealizowana ujemna różnica kursowa są używane do przeszacowywania otwartych transakcji i głównego konta księgi głównej.
- Na stronie **Konta przeszacowania waluty** wybierz walutę inną niż waluta konta przeszacowania dla każdej waluty i firmy. Jeśli nie zdefiniowano żadnych kont, używane są konta ze strony **Księga**.
- Na stronie **Parametry zarządzania gotówką i bankiem** dodaj sekwencję numerów dodanie sekwencji numerów dla aktualizacji wyceny waluty obcej **Sekwencje numerów**.


> [!NOTE]
> Jeśli firma używa rosyjskiego/polskiego lub węgierskiego kodu kraju/regionu, możesz już robić przeszacowanie w walucie obcej. Nie można używać przeszacowania w walucie obcej, używanego w innych krajach lub regionach.

## <a name="process-foreign-currency-revaluation"></a>Przetwarzanie przeszacowania w walucie obcej

Po zakończeniu instalacji za pomocą strony **przeszacowania w walucie obcej** w module Zarządzanie gotówką i bankami przeszacuj salda jednego lub wielu kont bankowych we wszystkich firmach. Można uruchomić proces w czasie rzeczywistym lub zaplanować uruchomienie przy użyciu zadania wsadowego.

Strona **Przeszacowania w walucie obcej** zawiera historię każdego procesu przeszacowania. Pokazuje, kiedy proces został uruchomiony i zdefiniowane kryteria, a także podaje łącze do załącznika, który został utworzony dla przeszacowania. Pokazuje także, czy poprzednie przeszacowanie zostało cofnięte. Aby uruchomić proces przeszacowania, zaznacz **przeszacowania w walucie obcej** w okienku akcji, aby otworzyć okno dialogowe **Bank — przeszacowanie w walucie obcej**.

Pole **Data przeszacowania** określa ostateczną datę obliczenia salda w walucie obcej, które ma być przeszacowane. Przeszacowane zostaną wszystkie transakcje, które zostały zrealizowane do tej daty.

Pole **Data kursu wymiany** określa datę kursu wymiany, która zostanie użyta do przeszacowywania salda w walutach. Na przykład można przeszacować salda począwszy od 31 stycznia, ale użyty jest kurs wymiany, który jest zdefiniowany dla 1 lutego.

Proces przeszacowania można uruchomić dla jednej lub wielu firm. Wyszukiwanie spowoduje wyświetlenie tylko tych firm, do których masz dostęp. Wybierz firmy, dla których chcesz wybrać konto bankowe, które kwalifikują się do przeszacowania w walucie obcej. Wszystkie konta bankowe dla tych firm będą wyświetlane w siatce.

Ustaw opcję **podglądu przed zaksięgowaniem** jako **tak**, jeśli chcesz sprawdzić wyniki przeszacowania przed jego zaksięgowaniem. Przeszacowanie w walucie obcej zawiera podgląd, który może zostać zaksięgowany. Nie trzeba ponownie uruchamiać procesu przeszacowania. Wyniki w podglądzie mogą być eksportowane do programu Microsoft Excel, aby zachować historię obliczania kwot. Jeżeli chcesz wyświetlić podgląd wyników przeszacowania, nie można użyć przetwarzania wsadowego.

Wybierz **OK**, aby przetworzyć przeszacowanie w walucie obcej. Aby dokładnie śledzić każde uruchomienie, jest tworzony rekord. Oddzielne rekordy są tworzone dla każdej firmy i warstwy księgowania.

## <a name="calculate-unrealized-gainloss"></a>Obliczanie niezrealizowanych dodatnich/ujemnych różnic kursowych

W module Zarządzanie gotówką i bankami waluta banku jest traktowana jako waluta podstawowa i nie zostanie przeszacowana. Saldo konta bankowego w walucie rozliczeniowej zostanie przeszacowane przy użyciu kursów wymiany między walutą banku a walutą rozliczeniową w polu **Data kursu wymiany**. Saldo konta bankowego w walucie raportowania zostanie przeszacowane przy użyciu kursów wymiany między walutą banku a walutą raportowania w polu **Data kursu wymiany**.

Zostanie utworzona transakcja dla różnic między saldem konta bankowego a nowym saldem, które zostanie obliczone dla waluty rozliczeniowej. Zostanie utworzona inna transakcja dla różnic między saldem konta bankowego a nowym saldem, które zostanie obliczone dla waluty raportowania. Wpisy dla tych transakcji są oznaczone jako uzgodnione. 

Nie jest tworzony zapis dla waluty rozliczeniowej, jeśli waluta banku odpowiada walucie rozliczeniowej. Podobnie, nie jest tworzony zapis dla waluty raportowania, jeśli waluta banku odpowiada walucie raportowania.

Transakcja przeszacowania w walucie obcej jest też podzielona na wymiary, które są dostępne w transakcji bankowych. Podział zależy od salda dla każdego wymiaru. Na przykład saldo bankowe wynosi 10 000, ale saldo jednostki biznesowej 001 wynosi 4000, saldo jednostki biznesowej 002 wynosi 6000. W takim przypadku 40 procent kwoty przeszacowania jest księgowane na koncie przeszacowania jednostki biznesowej 001, a 60 procent jest księgowane na koncie przeszacowania jednostki biznesowej 002. Jeśli struktura konta nie zawiera jednostki biznesowej, pełna kwota jest księgowana na koncie przeszacowania.

## <a name="reverse-foreign-currency-revaluation"></a>Wycofanie przeszacowania w walucie obcej

Jeśli musisz wycofać transakcję przeszacowania, kliknij przycisk **Wycofaj transakcję** znajdujący się na stronie **Przeszacowanie w walucie obcej** w okienku akcji. Zostanie utworzony nowy rekord historyczny przeszacowania w walucie obcej na potrzeby prowadzenia dziennika historii pokazującego, kiedy przeszacowania nastąpiły lub zostały wycofane.

Aby cofnąć kilka przeszacowań, musisz najpierw cofnąć najnowsze przeszacowanie. Następnie cofaj starsze przeszacowania według ich dat. Następnie można przetworzyć nowe przeszacowania dla okresów, w których przeszacowania zostały cofnięte.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
