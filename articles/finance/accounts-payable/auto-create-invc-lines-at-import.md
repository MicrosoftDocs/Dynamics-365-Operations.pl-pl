---
title: Generowanie wierszy faktury podczas importowania faktur od dostawcy
description: W tym artykule opisano funkcje automatycznego generowania wierszy faktur na fakturach od dostawcy podczas importowania faktur.
author: sunfzam
ms.date: 09/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: e745ab1fb39edf69fabd147e46e1da8cc98ba6e5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903515"
---
# <a name="generate-invoice-lines-when-you-import-vendor-invoices"></a>Generowanie wierszy faktury podczas importowania faktur od dostawcy

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym artykule opisano funkcje automatycznego generowania wierszy faktur na fakturach od dostawcy podczas importowania faktur.

Czasami faktury od dostawcy zawierają ograniczone informacje, takie jak informacje o odbiorcy i sumy częściowe. Nie zawierają jednak informacji o pozycjach w wierszach. Podczas importowania faktur wiersze faktury zostaną wygenerowane automatycznie na podstawie informacji o odpowiednim zamówieniu zakupu.

Aby włączyć automatyczne tworzenie wierszy faktury, wykonaj następujące kroki.

1.  Wybierz kolejno opcje **Rozrachunki z dostawcami \> Ustawienia \> Parametry modułu rozrachunków z dostawcami**.
2.  Na karcie **Automatyzacja faktury od dostawcy**, w obszarze **Automatyczne tworzenie wiersza dla zaimportowanych faktur** ustaw opcję **Automatycznie utwórz wiersze faktury** na **Tak**. 
4.  W polu **Wybierz domyślną ilość dla automatycznego tworzenia wierszy faktury** wybierz ilość, która ma być używana w systemie podczas automatycznego generowania wierszy faktury:

    - **Zamówiona ilość** — Wiersze będą generowane z wierszy zamówienia zakupu. Ta wartość jest wartością domyślną.
    - **Ilość na dokumencie przyjęcia produktów** — Numer zamówienia zakupu zostanie wykorzystany do znalezienia odpowiednich kwitów produktów. Następnie użyje on ilości z dokumentu przyjęcia produktów do wygenerowania wierszy faktury.

## <a name="data-entity-changes"></a>Zmiany encji danych

Obsługa funkcji opisanej w tym artykule została rozszerzona o encję danych **Nagłówek faktury od dostawcy**. Dodano trzy pola:

- **HeaderOnlyImport** — w tym polu musi być ustawiona wartość **Yes**, aby generować wiersze dla nagłówków faktur.
- **PurchIdRange** — lista numerów zamówień zakupu. Numery faktur mogą być zakresami, takimi jak **INV0001..INV0009** (gdzie dwa kropki oddzielają początek i koniec zakresu), lub wartościami dyskretnymi, takimi jak **INV0001, INV0003, INV0006**. Wszystkie zamówienia zakupu muszą należeć do tego samego konta dostawcy w nagłówku faktury. W przeciwnym razie zostanie wyświetlony następujący komunikat o błędzie: „Nie można wygenerować wierszy faktury. Zamówienia zakupu mają różne konta dostawców”.
- **PackingslipRange** — lista numerów dokumentów przyjęcia produktów. Wiersze faktury od dostawcy można tworzyć z dokumentów przyjęcia produktów. Jednak numery dokumentów przyjęcia produktów nie są zwykle uwzględnione na fakturach od dostawcy. W tym polu należy wprowadzać numery dokumentów przyjęcia produktów tylko wtedy, gdy istnieje możliwość jednoznacznej identyfikacji dokumentów przyjęcia produktów dla określonych faktur. Wiersze faktury można generować na podstawie dokumentów przyjęcia produktów. Jeśli to pole jest używane, ustawienie w polu **Wybierz domyślną ilość dla automatycznego tworzenia wierszy faktury** na stronie **Parametry rozrachunków z dostawcami** jest ignorowane. 

**Ograniczenie:** jeśli wprowadzisz wiele numerów dokumentów przyjęcia produktów, zostanie utworzonych kilka oczekujących faktur od dostawcy o tym samym numerze faktury. Przed dalszym przetwarzaniem faktury należy je skonsolidować ręcznie. W przyszłych wersjach planujemy konsolidować faktury automatycznie, więc ograniczenie zostanie usunięte.

Wszystkie dokumenty przyjęcia produktów muszą należeć do tego samego konta dostawcy w nagłówku faktury.

## <a name="result"></a>Wynik

Jeśli wiersze zostaną pomyślnie wygenerowane, w historii automatyzacji faktur od dostawcy zostanie zarejestrowany następujący komunikat: „Automatycznie twórz wiersze faktury: powiodło się”.

Jeśli wiersze nie są generowane, rejestrowany jest następujący komunikat o błędzie: „Automatycznie twórz wiersze faktury: nie powiodło się”.
