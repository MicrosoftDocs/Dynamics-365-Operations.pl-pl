---
title: Sprawdzanie jakości towarów
description: W tym temacie opisano sposób przetwarzania zleceń kontroli jakości.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ceb5547b6c1d4c44e53faba0d6e2c1f0368fb95768a2520ecc39066ff73a03d2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755377"
---
# <a name="inspect-the-quality-of-goods"></a>Sprawdzanie jakości towarów

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób przetwarzania zleceń kontroli jakości. Kontrole jakości są zazwyczaj wykonywane przez pracownika ds. kontroli jakości.

Jeśli są zainstalowane standardowe dane demonstracyjne, możesz użyć ich do wykonania procedur standardowych w tym temacie. Aby użyć danych demonstracyjnych, należy wybrać firmę *USMF* przed rozpoczęciem. Następnie musisz potwierdzić zamówienie zakupu *000016* i zatwierdzić dokument przyjęcia produktów. Zlecenie kontroli jakości zostanie wygenerowane automatycznie.

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
