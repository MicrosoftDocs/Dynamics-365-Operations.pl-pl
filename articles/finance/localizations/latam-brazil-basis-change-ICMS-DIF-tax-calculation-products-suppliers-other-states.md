---
title: Zmiana podstawy w obliczeniach podatku ICMS-DIF dla produktów od dostawców z innych stanów
description: W tym temacie opisano konfigurację obliczania typu podatku ICMS-DIF w przypadku, gdy dokument fiskalny jest odbierany w stanie Brazylijskie do Dos lub Wyspy Świętego Wsadowego (SP).
author: Kai-Cloud
ms.date: 1/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-1-17
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 16f78b85567e6d08c588e621119513ff070bf618
ms.sourcegitcommit: 68655c5673aef9892063e5913ffee6bfc3817387
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/21/2022
ms.locfileid: "8016176"
---
# <a name="basis-change-in-icms-dif-tax-calculations-for-products-from-suppliers-in-other-states"></a>Zmiana podstawy w obliczeniach podatku ICMS-DIF dla produktów od dostawców z innych stanów

W tym temacie opisano konfigurację obliczania typu podatku **ICMS-DIF** w przypadku, gdy dokument fiskalny jest odbierany w stanie Brazylijskie do Dos lub Wyspy Świętego Wsadowego (SP).

Zgodnie z definicją w ustawie państwowej zebranemu przez system Imposto sobre Tychulação de Mercadorias e Serviços (ICMS) należy użyć następującej reguły:

*ICMS do zbierania* = ([(*Kwota operacji* – *ICMS ze źródła*) ÷ (1 – *ICMS % wewnętrzny*)] × *ICMS % wewnętrznych*) – kwota *ICMS ze źródła*

## <a name="example"></a>Przykład

Firma brazylijskia ze stanem RS otrzymuje dokument fiskalny na zakup od dostawcy ze stanem SP. Firma musi zbierać procentową różnicę między ICMS między województwem RS (18 procent) a województwem SP (12 procent). Podstawa musi być jednak obliczona zgodnie z poprzednią regułą.

- **Kwota operacji:** 1 000,00 realiów brazylijskich (R$ 1 000,00)
- **Stan międzystanowy ICMS:** 120,00 USD
- **Procent ICMS w stanie RS:** 18 procent
- **ICMS do odbioru w województwie:** (\[1000 – 120) ÷ (1 – 0,18)\] × 0,18 ) – 120 = R$ 73,17 

## <a name="resolution"></a>Rozwiązanie

Aby obliczyć kwotę różnicy ICMS (ICMS-DIF) zgodnie z regułami stanu RS, należy skonfigurować kody podatków oraz grupę podatków w następujący sposób:

1. Umożliwia utworzenie kodu podatku służącego do otrzymywania 12-procentowego podatku ICMS (dla drugiego województwa). Ten kod służy do rejestrowania kwoty podatku dochodowego od dostawcy.
2. Utwórz kod podatku, aby zbierać ICMS-DIF. Ten kod podatku powinien mieć kwotę procentową w wysokości 18 procent (dla własnego województwa), aby zdefiniować różnicę między 18 a 12 procentami. Ustaw typ podatku **ICMS-DIF**. Ten kod podatku musi być zdefiniowany w następujący sposób w parametrach obliczania:

    - W polu **Pochodzenie** wybierz pozycję **Procent od kwoty brutto**.
    - W polu **Podstawa marginesu** wybierz **wartość netto na wiersz** lub **kwotę netto salda faktury**.
    - Kod opodatkowania należy zdefiniować tak, aby jego wartość podatkowa wynosi **3**. W ten sposób transakcja korekty zostanie utworzona automatycznie po włączeniu **modułu Księgi podatkowe**.
    - W konfiguracji grupy podatków wybierz opcję **Użyj podatku** dla kodu podatku **ICMS-DIF**.
