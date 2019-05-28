---
title: Definicje księgowania
description: Ten artykuł zawiera przykłady pokazujące, jak definicje księgowania są używane dla przyszłych zobowiązań wiążących w zamówieniach zakupu i dla asygnat budżetu.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15772
ms.assetid: 3864e4da-853f-403d-b906-79631d80b363
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5fb08a86639e9a9a79dca5fc1200e73e5870432
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564700"
---
# <a name="posting-definition-examples"></a>Szablony definicji księgowania

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera przykłady pokazujące, jak definicje księgowania są używane dla przyszłych zobowiązań wiążących w zamówieniach zakupu i dla asygnat budżetu.

Zanim przeczytasz ten temat, zapoznaj się z definicjami księgowania i definicjami księgowania transakcji. Więcej informacji znajdziesz w temacie [Definicje księgowania](posting-definitions.md). Poniższe przykłady można skonfigurować na stronie **Definicje księgowania**. Każdy przykład zawiera następujące sekcje:

-   Definicja księgowania — kryteria uzgadniania
-   Definicja księgowania — wygenerowane zapisy
-   Transakcje z kontami, wartości wymiarów i kwoty
-   Wpisy w księdze wygenerowane z definicji księgowania

Kiedy wystąpi dopasowanie między wartościami kont i wymiarów w okienku **Kryteria dopasowania** dla definicji księgowania i wartościami kont i wymiarów w transakcji, generowane są zapisy księgi na podstawie okienka **Wygenerowane zapisy** dla danej definicji księgowania. 
> [!NOTE]
> Definicję księgowania można skojarzyć z konkretnym typem transakcji na stronie **Definicje księgowania transakcji**. Po skojarzeniu definicji księgowania z typem transakcji i wybraniu opcji **Użyj definicji księgowania** na stronie **Parametry księgi głównej** wszystkie transakcje wybranego typu muszą korzystać z definicji księgowania.

## <a name="example-purchase-order-encumbrances"></a>Przykład: Przyszłe zobowiązania wiążące dla zamówień zakupu
Po włączeniu przetwarzania przyszłych zobowiązań wiążących przez zaznaczenie opcji **Włącz przetwarzanie przyszłych zobowiązań wiążących** na stronie **Parametry księgi głównej**, definicje księgowania muszą zostać użyte do rejestrowania przyszłych zobowiązań wiążących w księdze głównej dla dowolnych kont, które powinny być rezerwowane. W większości przypadków wszystkie konta wydatków są rezerwowane w bilansie. 

Definicje księgowania dla przyszłych zobowiązań wiążących ustawia się dla modułu **Zakupy** na stronie **Definicje księgowania**. Następnie w obszarze **Zakupy** na stronie **Definicji księgowania transakcji** można wybrać typ transakcji **Zamówienie zakupu**, aby skojarzyć definicję księgowania z zamówieniami zakupu. 

Wszystkie transakcje załącznika dla przyszłych zobowiązań wiążących z zamówień zakupu muszą się bilansować (tj. strony „winien” i „ma” muszą się równoważyć) w każdym niepowtarzalnym wymiarze załącznika.

### <a name="posting-definition--match-criteria"></a>Definicja księgowania — kryteria uzgadniania

| Struktura konta       | Dopasuj numer konta | Priorytet  |
|-------------------------|----------------------|----------|
| Struktura konta — zyski i straty | \*                   | 1        |

<em>Pusta wartość w polu **Dopasuj numer konta oznacza</em>*, że wszystkie pasujące konta w definiowanej strukturze konta są częścią reguły uzgadniania.

### <a name="posting-definition--generated-entries"></a>Definicja księgowania — wygenerowane zapisy

| Struktura konta | Wygenerowany numer konta                    | Wygenerowany debet/kredyt |
|-------------------|---------------------------------------------|------------------------|
| Saldo           | 300143 - -(Konto przyszłego zobowiązania wiążącego)             | To samo                   |
| Saldo           | 300144 - -(Rezerwa dla konta przyszłego zobowiązania wiążącego) | Balansowanie              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a>Transakcje z kontami, wartości wymiarów i kwoty

Kont i wartości wymiarów pochodzą z zasad podziału księgowań wprowadzonych dla wiersza zamówienia zakupu lub z kont i wymiarów, które są generowane automatycznie na podstawie wartości domyślnych dla dostawców, towarów, kategorii i szablonów wymiaru.

| Konto + wymiary           | Strona debetowa  | Strona kredytowa | Komentarz |
|--------------------------------|--------|--------|---------|
| 606400-OU\_1-OU\_3566-Szkolenie | 250.00 |        |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a>Wpisy w księdze wygenerowane z definicji księgowania

Wygenerowane zapisy księgi są tworzone w celu rejestracji przyszłych zobowiązań wiążących.

| Konto + wymiary           | Strona debetowa  | Strona kredytowa | Komentarz |
|--------------------------------|--------|--------|---------|
| 300143-OU\_1-OU\_3566-Szkolenie | 250.00 |        |         |
| 300144-OU\_1-OU\_3566-Szkolenie |        | 250.00 |         |

W tym przykładzie dowolne konto będące częścią Struktury konta — zyski i straty spełnia kryteria definicji księgowania. Dlatego podczas szacowania 606500-OU\_1-OU\_3566-Szkolenie wygenerowane zapisy są tworzone dla kont, które są zdefiniowane w okienku **Wygenerowane zapisy** dla definicji księgowania.

## <a name="example-budget-appropriations"></a>Przykład: asygnaty budżetu
Po włączeniu asygnaty budżetu przez zaznaczenie opcji **Włączanie asygnaty budżetu** na stronie **Parametry księgi głównej** definicje księgowania muszą być używane do rejestrowania wpisów do rejestru budżetu w księdze głównej. Jeśli konfiguracji kontroli budżetu jest aktywna i włączona, definicje księgowania i definicje księgowania transakcji mogą być używane do obsługi rejestracji zapisów dla asygnat, korekt, przeniesień, projektów, środków trwałych i prognoz popytu i dostaw w księdze głównej. 

Aby skonfigurować definicję księgowania dla wpisów do rejestru budżetu, która ma typ budżetu **Budżet pierwotny** i która ma włączone asygnaty, wybierz moduł **Budżet** na stronie **Definicje księgowania**. Następnie w obszarze **Budżet** na stronie **Definicje księgowania transakcji** można użyć kodów budżetu do skojarzenia definicji księgowania z wpisów do rejestru budżetu o typie **Budżet pierwotny**. 

Jeśli asygnaty budżetu i definicje księgowania są włączone, wpisy do rejestru budżetu są rejestrowane dla kontroli budżetu i w księdze głównej.

### <a name="posting-definition--match-criteria"></a>Definicja księgowania — kryteria uzgadniania

| Struktura konta       | Dopasuj numer konta | Priorytet  |
|-------------------------|----------------------|----------|
| Struktura konta — zyski i straty | \*                   | 1        |

<em>Pusta wartość w polu **Dopasuj numer konta oznacza</em>*, że wszystkie pasujące konta w definiowanej strukturze konta są częścią reguły uzgadniania.

### <a name="posting-definition--generated-entries"></a>Definicja księgowania — wygenerowane zapisy

| Struktura konta | Wygenerowany numer konta              | Wygenerowany debet/kredyt |
|-------------------|---------------------------------------|------------------------|
| Struktura konta | 300145 - -(Szacowane konto przychodów) | To samo                   |
| Struktura konta | 300146 - -(Konto asygnaty)     | Balansowanie              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a>Transakcje z kontami, wartości wymiarów i kwoty

Konta, wartości wymiarów i kwoty dla zapisu na koncie budżetu wprowadza się na stronie **Wpis do rejestru budżetu**.

| Konto + wymiary           | Strona debetowa | Strona kredytowa | Komentarz |
|--------------------------------|-------|--------|---------|
| 606400-OU\_1-OU\_3566-Szkolenie |       | 250.00 |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a>Wpisy w księdze wygenerowane z definicji księgowania

Wygenerowane zapisy księgi są tworzone w celu rejestracji pierwotnego budżetu w każdym wymiarze.

| Konto + wymiary           | Strona debetowa  | Strona kredytowa | Komentarz |
|--------------------------------|--------|--------|---------|
| 300145-OU\_1-OU\_3566-Szkolenie |        | 250.00 |         |
| 300146-OU\_1-OU\_3566-Szkolenie | 250.00 |        |         |

W tym przykładzie dowolne konto będące częścią Struktury konta — zyski i straty spełnia kryteria definicji księgowania. Dlatego podczas szacowania 606400-OU\_1-OU\_3566-Szkolenie tworzone są wygenerowane zapisy księgi.





