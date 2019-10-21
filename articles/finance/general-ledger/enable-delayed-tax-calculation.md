---
title: Włącz opóźnione obliczanie podatku w arkuszu
description: W tym temacie objaśniono sposób używania funkcji **Włącz opóźnione obliczanie podatku dla arkusza** w celu zwiększenia wydajności obliczania podatku, gdy objętość wierszy arkusza jest duża.
author: ericwang
manager: Ann Beebe
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 5a8ae30a007d3e2b8b7a9bc9eb7786f6e58246d0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179367"
---
# <a name="enable-delayed-tax-calculation-on-journal"></a>Włącz opóźnione obliczanie podatku w arkuszu
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie objaśniono sposób używania funkcji **Włącz opóźnione obliczanie podatku dla arkusza** w celu zwiększenia wydajności obliczania podatku, gdy objętość wierszy arkusza jest duża.

Bieżące zachowanie przy obliczaniu podatku w arkuszu jest wyzwalane w czasie rzeczywistym, gdy użytkownik zaktualizuje pola związane z podatkiem, np. grupę podatków/grupę podatków dla towaru. Każda aktualizacja na poziomie wiersza arkusza ponownie obliczy kwotę podatku we wszystkich wierszach arkusza. Ułatwia użytkownikowi wyświetlanie obliczonej kwoty podatku w czasie rzeczywistym, ale może również spowodować, że powodować problemy wydajności jeśli liczba wierszy w arkuszu jest duża.

Ta funkcja stanowi opcję opóźnienia obliczania podatku w celu rozwiązania problemów z wydajnością. Jeśli ta funkcja jest włączona, kwota podatku będzie obliczana tylko wtedy, gdy użytkownik kliknie przycisk „podatek” lub zaksięguje arkusz.

Użytkownik może włączać/wyłączać parametr na trzech poziomach:
- Według firmy
- Nazwa arkusza
- Nagłówek arkusza

System przyjmie wartość parametru w nagłówku arkusza jako wersję ostateczną. Wartość parametru w nagłówku arkusza będzie domyślnie określana na podstawie nazwy arkusza. Podczas tworzenia nazwy arkusza wartość parametru w polu nazwa arkusza jest ustawiana domyślnie na podstawie wartości parametru księgi głównej

Wartości pól „rzeczywista kwota podatku” i „obliczona kwota podatku” w arkuszu zostaną ukryte, jeśli ten parametr jest włączony Celem jest nie wprowadzać użytkownika w błąd, ponieważ wartość tych dwóch pól będzie zawsze wynosiła 0 przed rozpoczęciem obliczenia podatku przez użytkownika.

## <a name="enable-delayed-tax-calculation-by-legal-entity"></a>Włącz opóźnione obliczanie podatku według firm

1. Wybierz kolejno opcje **Księga główna > Ustawienia księgi > Parametry księgi głównej**
2. Kliknij kartę **Podatek**.
3. Na skróconej karcie **Ogólne** znajdź parametr **Obliczanie podatku opóźnionego**, włącz/wyłącz

![](media/delayed-tax-calculation-gl.png)



## <a name="enable-delayed-tax-calculation-by-journal-name"></a>Włącz opóźnione obliczanie podatku w arkuszu po nazwie arkusza

1. Wybierz kolejno opcje **Księga główna > Konfiguracja arkusza > Nazwy arkuszy**
2. Na skróconej karcie **Ogólne** znajdź parametr **Obliczanie podatku opóźnionego**, włącz/wyłącz

![](media/delayed-tax-calculation-journal-name.png)

## <a name="enable-delayed-tax-calculation-by-journal"></a>Włącz opóźnione obliczanie podatku po arkuszu

1. Wybierz kolejno **Księga główna > Wpisy w arkuszu > Arkusze finansowe**.
2. Kliknij przycisk **Nowy**
3. Wybierz nazwę arkusza
4. Kliknij przycisk **Ustawienia**
5. Znajdź parametr **Obliczanie podatku opóźnionego**, włącz/wyłącz

![](media/delayed-tax-calculation-journal-header.png)
