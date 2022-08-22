---
title: Sprawdzanie jakości towarów
description: W tym artykule opisano sposób przetwarzania zleceń kontroli jakości.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b881f9c6f872061864d4254ce880d981ca71c479
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219043"
---
# <a name="inspect-the-quality-of-goods"></a>Sprawdzanie jakości towarów

[!include [banner](../../includes/banner.md)]

W tym artykule opisano sposób przetwarzania zleceń kontroli jakości. Kontrole jakości są zazwyczaj wykonywane przez pracownika ds. kontroli jakości.

Jeśli są zainstalowane standardowe [dane demonstracyjne](../../../fin-ops-core/fin-ops/get-started/demo-data.md), możesz użyć ich do wykonania procedur standardowych w tym artykule. Aby użyć danych demonstracyjnych, należy wybrać firmę *USMF* przed rozpoczęciem. Następnie musisz potwierdzić zamówienie zakupu *000016* i zatwierdzić dokument przyjęcia produktów. Zlecenie kontroli jakości zostanie wygenerowane automatycznie.

## <a name="step-1-select-a-quality-order"></a>Krok 1: Wybieranie zlecenia kontroli jakości

Aby wybrać zlecenie kontroli jakości, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Zlecenia kontroli jakości**.
1. Przed rozpoczęciem tej procedury wybierz wygenerowane zlecenie kontroli jakości.

## <a name="step-2-record-test-results"></a>Krok 2: Rejestrowanie wyników testów

Aby zarejestrować wyniki testów, wykonaj następujące kroki.

1. Wybierz opcję **Wyniki**.
1. Wybierz opcję **Edycja**.
1. W polu **Liczba wyników** wprowadź liczbę.
1. W polu **Wynik** wybierz pożądany rekord. W tym przykładzie wynik bazuje na wstępnie zdefiniowanym wyniku. Zazwyczaj rejestruje się bardziej szczegółowy wynik testu, na przykład rozmiar lub inny wymiar.
1. Wybierz opcję **Zapisz**.
1. Zamknij stronę.

## <a name="step-3-validate-the-quality-order"></a>Krok 3: Sprawdzanie poprawności zlecenia kontroli jakości

Aby sprawdzić poprawność zlecenia kontroli jakości, należy wykonać następujące czynności.

1. Wybierz **Potwierdź**.
1. W polu **Poprawność sprawdzona przez** wybierz użytkownika, który wykonuje inspekcję.
1. Wybierz pozycję **Wybierz**.
1. Kliknij przycisk **OK**.
1. Zamknij stronę.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
