---
title: Odwołania do oryginalnych faktur w fakturach korygujących
description: W tym artykule wyjaśniono, jak skonfigurować i wydrukować numery oryginalnych faktur w powiązanych fakturach korygujących.
author: mrolecki
ms.date: 10/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.search.form: ''
ms.openlocfilehash: f1f9ca3914aa02cc38ddfe9f8dd88eb7fc88fd4b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281244"
---
# <a name="references-to-original-invoices-in-credit-notes"></a>Odwołania do oryginalnych faktur w fakturach korygujących

[!include [banner](../includes/banner.md)]


W niektórych krajach i regionach istnieje wymóg prawny, aby wydrukowane noty kredytowe zawierały odniesienia do oryginalnych faktur. W tym artykule wyjaśniono, jak skonfigurować i wydrukować numery oryginalnych faktur w powiązanych fakturach korygujących.

## <a name="prerequisites"></a>Wymagania wstępne

- W obszarze roboczym **Zarządzanie funkcjami** włącz funkcję **Układ faktur kredytowych dla raportów faktur sprzedaży i projektów**. Aby uzyskać więcej informacji, zapoznaj się z tematem [Zarządzanie funkcjami — omówienie](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Formaty do drukowania wymaganych dokumentów muszą być skonfigurowane w zarządzaniu drukowaniem.

Funkcje opisane w tym artykule dotyczą następujących dokumentów:

**Rozrachunki z odbiorcami**

- Niezależna faktura korygująca
- Odbiorca faktury korygującej

**Zarządzanie projektami i ich księgowanie**

- Projektowanie faktury korygującej

## <a name="configure-accounts-receivable-parameters"></a>Konfiguruj Parametry modułu rozrachunków z odbiorcami

Aby ustawić parametr sterujący tym, czy odwołania do oryginalnych faktur mają być drukowane w powiązanych fakturach korygują, należy wykonać następujące kroki.

1. Wybierz kolejno pozycje **Rozrachunki z odbiorcami** \> **Ustawienia** \> **Parametry modułu rozrachunków z odbiorcami**.
2. Na karcie **Aktualizacje** na skróconej karcie **Faktura** ustaw opcję **Zastosuj układ faktur kredytowych w raportach faktur sprzedaży i projektów** na wartość **Tak**.

![Konfiguruj Parametry modułu rozrachunków z odbiorcami.](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a>Zdefiniuj odniesienia do oryginalnych faktur

Poniższe procedury służą do definiowania odniesień do oryginalnych faktur na podstawie typu dokumentu.

### <a name="free-text-credit-note"></a>Niezależna faktura korygująca

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Faktury** \> **Wszystkie faktury niezależne**.
2. Utwórz nową notę kredytową lub wybierz istniejącą notę kredytową.
3. Otwórz fakturę.
4. W okienku akcji na karcie **Faktura** w grupie **Funkcje** wybierz **Księgowanie fakturowania po stronie kredytowej**.
5. Wprowadź odwołanie do oryginalnej faktury i wybierz przyczynę korekty.

![Definiowanie odwołania dla faktury elektronicznej.](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a>Odbiorca faktury korygującej

1. Przejdź do pozycji **Rozrachunki z odbiorcami** \> **Zamówienia** \> **Wszystkie zamówienia sprzedaży**.
2. Wybierz i otwórz zafakturowane zamówienie sprzedaży, które musi zostać skorygowane.
3. W okienku akcji na karcie **Sprzedaj** w grupie **Nota kredytowa** wybierz **Nota kredytowa**.
4. Wpisz powód korekty. Automatycznie zostanie utworzone odwołanie do oryginalnej faktury.

![Definiowanie odwołania do zamówienia sprzedaży.](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a>Projektowanie faktury korygującej

1. Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Faktury projektu** \> **Faktury projektu**.
2. Wybierz i otwórz fakturę za projekt, która musi zostać poprawiona.
3. W okienku akcji na karcie **Faktura projektu** w grupie **Funkcje** wybierz **Wybierz do faktury korygującej**.
4. Wybierz **Księgowanie fakturowania po stronie kredytowej**.
5. Wpisz powód korekty. Automatycznie zostanie utworzone odwołanie do oryginalnej faktury.

![Definiowanie odwołania dla faktury do projektu.](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a>Drukowanie faktur korygujących

Gdy drukujesz dowolny tekst, noty kredytowe klienta i projektu, będą one zawierać odniesienie do oryginalnej faktury i powód korekty.

![Drukowanie faktury korygującej.](media/credit-note-FTI.jpg)

> [!NOTE]
> Upewnij się, że formaty dokumentów do druku są poprawnie skonfigurowane, przy założeniu, że zostaną wydrukowane odniesienia do oryginalnych faktur.

## <a name="references-to-original-invoices-in-debit-notes"></a>Odwołania do oryginalnych faktur w notach uznaniowych

Domyślnie w fakturach korygujących można wprowadzić odwołania do oryginalnych faktur. Na przykład można wprowadzać odwołania w przypadku ujemnych (zmniejszających) korekt oryginalnych faktur.

Aby wprowadzać odwołania podczas wprowadzania dodatnich (rosnących) korekt oryginalnych faktur, należy włączyć funkcję **Odwołania do oryginalnych faktur w notach uznaniowych** w obszarze roboczym **Zarządzanie funkcjami**.  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
