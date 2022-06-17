---
title: Cofanie ustawień arkuszy i wierszy
description: W tym artykule opisano powody, dla których wpis wycofania wprowadzony dla arkusza finansowego mógł nie zostać uwzględniony w ramach zaksięgowanej transakcji.
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
ms.openlocfilehash: e36a3ea1736e4d7f60a5a6ce588ad3e66c950c14
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899850"
---
# <a name="reverse-settings-on-journals-and-lines"></a>Cofanie ustawień arkuszy i wierszy

[!include [banner](../includes/banner.md)]

W tym artykule opisano powody, dla których wpis wycofania wprowadzony dla arkusza finansowego mógł nie zostać uwzględniony w ramach zaksięgowanej transakcji.  

## <a name="symptom"></a>Objaw

Arkusz finansowy zawiera wpis wycofania i datę wycofania w arkuszu. Podczas księgowania arkusza żadne załączniki nie są wycofywane. Dlaczego tak się dzieje?

## <a name="resolution"></a>Rozwiązanie

Podczas księgowania arkusza proces wycofywania uwzględnia wyłącznie ustawienia **Wpis wycofania** oraz **Data wycofania** z sekcji **Wiersze** załącznika. Dzięki temu arkusz może obejmować wybrane załączniki oznaczone jako przeznaczone do wycofania, a także takie, które nie mają takiego oznaczenia.

Wartości z arkusza są używane jedynie jako wartości domyślne podczas dodawania *nowych* wierszy. Zmiana wartości w arkuszu nie wpływa na istniejące wiersze. W tym przykładzie wiersze załącznika zostały wprowadzone wcześniej. Jeśli użytkownik wpisze szczegóły wiersza przed oznaczeniem arkusza jako arkusza wycofania, oznaczenia wpisu wycofania i daty wycofania nie będą mieć zastosowana do żadnych istniejących wierszy.

Zmiana wpisu wycofania lub daty wycofania istniejącego wiersza powoduje zastosowanie zmiany do innych wierszy w tym samym załączniku. Aby zoptymalizować wydajność, siatka nie jest odświeżana po zastosowaniu zmian do innych wierszy. Zaktualizowane wartości można wyświetlić, odświeżając siatkę.


