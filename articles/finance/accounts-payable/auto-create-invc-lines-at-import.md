---
title: Generowanie wierszy faktury podczas importowania faktur od dostawcy
description: W tym temacie opisano funkcje automatycznego generowania wierszy faktur na fakturach od dostawcy podczas importowania faktur.
author: sunfzam
ms.date: 09/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 87dec3c142ae296975ab98432421be4548085c80
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647905"
---
# <a name="generate-invoice-lines-when-you-import-vendor-invoices"></a>Generowanie wierszy faktury podczas importowania faktur od dostawcy

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie opisano funkcje automatycznego generowania wierszy faktur na fakturach od dostawcy podczas importowania faktur.

Czasami faktury od dostawcy zawierają ograniczone informacje, takie jak informacje o odbiorcy i sumy częściowe. Nie zawierają jednak informacji o pozycjach w wierszach. Podczas importowania faktur system może automatycznie generować wiersze faktury na podstawie informacji z odpowiedniego zamówienia zakupu.

Aby włączyć automatyczne tworzenie wierszy faktury, wykonaj następujące kroki.

1.  Wybierz kolejno opcje **Rozrachunki z dostawcami \> Ustawienia \> Parametry modułu rozrachunków z dostawcami**.
2.  Na karcie **Automatyzacja faktury od dostawcy**, w obszarze **Automatyczne tworzenie wiersza dla zaimportowanych faktur** ustaw opcję **Automatycznie utwórz wiersze faktury** na **Tak**. 
4.  W polu **Wybierz domyślną ilość dla automatycznego tworzenia wierszy faktury** wybierz ilość, która ma być używana w systemie podczas automatycznego generowania wierszy faktury:

    - **Zamówiona ilość** — system wygeneruje wiersze z wierszy zamówienia zakupu. Ta wartość jest wartością domyślną.
    - **Ilość na dokumencie przyjęcia produktów** — system będzie używać numerów zamówień zakupu w celu znalezienia odpowiednich dokumentów przyjęcia produktów. Następnie użyje on ilości z dokumentu przyjęcia produktów do wygenerowania wierszy faktury.

## <a name="data-entity-changes"></a>Zmiany encji danych

Obsługa funkcji opisanej w tym temacie została rozszerzona o encję danych **Nagłówek faktury od dostawcy**. Dodano trzy pola:

- **HeaderOnlyImport** — w tym polu musi być ustawiona wartość **Yes**, aby system generował wiersze dla nagłówków faktur.
- **PurchIdRange** — lista numerów zamówień zakupu. Numery faktur mogą być zakresami, takimi jak **INV0001..INV0009** (gdzie dwa kropki oddzielają początek i koniec zakresu), lub wartościami dyskretnymi, takimi jak **INV0001, INV0003, INV0006**. Wszystkie zamówienia zakupu muszą należeć do tego samego konta dostawcy w nagłówku faktury. W przeciwnym razie zostanie wyświetlony następujący komunikat o błędzie: „Nie można wygenerować wierszy faktury. Zamówienia zakupu mają różne konta dostawców”.
- **PackingslipRange** — lista numerów dokumentów przyjęcia produktów. Wiersze faktury od dostawcy można tworzyć z dokumentów przyjęcia produktów. Jednak numery dokumentów przyjęcia produktów nie są zwykle uwzględnione na fakturach od dostawcy. W tym polu należy wprowadzać numery dokumentów przyjęcia produktów tylko wtedy, gdy istnieje możliwość jednoznacznej identyfikacji dokumentów przyjęcia produktów dla określonych faktur. Wiersze faktury można generować na podstawie dokumentów przyjęcia produktów. I jeśli to pole jest używane, ustawienie w polu **Wybierz domyślną ilość dla automatycznego tworzenia wierszy faktury** na stronie **Parametry rozrachunków z dostawcami** jest ignorowane. 

**Ograniczenie:** jeśli wprowadzisz wiele numerów dokumentów przyjęcia produktów, zostanie utworzonych kilka oczekujących faktur od dostawcy o tym samym numerze faktury. Przed dalszym przetwarzaniem faktury należy je skonsolidować ręcznie. W przyszłych wersjach zamierzamy umożliwić systemowi automatyczną konsolidację faktur, w związku z tym ograniczenie zostanie usunięte.

Wszystkie dokumenty przyjęcia produktów muszą należeć do tego samego konta dostawcy w nagłówku faktury.

## <a name="result"></a>Wynik

Jeśli system pomyślnie wygeneruje wiersze, w historii automatyzacji faktur od dostawcy zostanie zarejestrowany następujący komunikat: „Automatyczne tworzenie wierszy faktury: Zakończone pomyślnie”.

Jeśli system nie wygeneruje wierszy, zostanie zarejestrowany następujący komunikat o błędzie: „Automatyczne tworzenie wierszy faktury: Zakończone niepowodzeniem”.
