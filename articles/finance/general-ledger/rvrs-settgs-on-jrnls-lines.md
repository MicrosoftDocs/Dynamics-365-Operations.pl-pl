---
title: Cofanie ustawień arkuszy i wierszy
description: W tym temacie opisano powody, dla których wpis wycofania wprowadzony dla arkusza finansowego mógł nie zostać uwzględniony w ramach zaksięgowanej transakcji.
author: kweekley
ms.date: 04/29/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ff8c0bda8e750e95261039b373cfb96a76034f6f
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724453"
---
# <a name="reverse-settings-on-journals-and-lines"></a>Cofanie ustawień arkuszy i wierszy

[!include [banner](../includes/banner.md)]

W tym temacie opisano powody, dla których wpis wycofania wprowadzony dla arkusza finansowego mógł nie zostać uwzględniony w ramach zaksięgowanej transakcji.  

## <a name="symptom"></a>Objaw

Arkusz finansowy zawiera wpis wycofania i datę wycofania w arkuszu. Podczas księgowania arkusza żadne załączniki nie są wycofywane. Dlaczego tak się dzieje?

## <a name="resolution"></a>Rozwiązanie

Podczas księgowania arkusza proces wycofywania uwzględnia wyłącznie ustawienia **Wpis wycofania** oraz **Data wycofania** z sekcji **Wiersze** załącznika. Dzięki temu arkusz może obejmować wybrane załączniki oznaczone jako przeznaczone do wycofania, a także takie, które nie mają takiego oznaczenia.

Wartości z arkusza są używane jedynie jako wartości domyślne podczas dodawania *nowych* wierszy. Zmiana wartości w arkuszu nie wpływa na istniejące wiersze. W tym przykładzie wiersze załącznika zostały wprowadzone wcześniej. Jeśli użytkownik wpisze szczegóły wiersza przed oznaczeniem arkusza jako arkusza wycofania, oznaczenia wpisu wycofania i daty wycofania nie będą mieć zastosowana do żadnych istniejących wierszy.

Zmiana wpisu wycofania lub daty wycofania istniejącego wiersza powoduje zastosowanie zmiany do innych wierszy w tym samym załączniku. Aby zoptymalizować wydajność, siatka nie jest odświeżana po zastosowaniu zmian do innych wierszy. Zaktualizowane wartości można wyświetlić, odświeżając siatkę.


