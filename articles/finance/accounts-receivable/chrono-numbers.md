---
title: Chronologicznie numerowanie dokumentów i załączników
description: W tym artykule wyjaśniono, jak skonfigurować i używać numerów chronologicznych dla odpowiednich dokumentów i powiązanych faktur obcych.
author: ikond
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceGroup
audience: Application User
ms.reviewer: kfend
ms.custom: 401195
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-15
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 6baf307406982e8f72acc0d02f047dbc7c63a5ed
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876391"
---
# <a name="numbering-documents-and-vouchers-chronologically"></a>Chronologicznie numerowanie dokumentów i załączników

[!include [banner](../includes/banner.md)]


W niektórych krajach istnieje prawny wymóg numeracji dokumentów i powiązanych załączników w porządku chronologicznym. Chronologia musi być obsługiwana według okresów. Wszystkie numery należące do poprzednich okresów muszą być mniejsze od numerów należących do późniejszych okresów. Aby spełnić to wymaganie, zaimplementowano funkcje numerowania chronologicznego. W tym artykule wyjaśniono, jak skonfigurować i używać numerów chronologicznych dla odpowiednich dokumentów i powiązanych faktur obcych.

## <a name="prerequisites"></a>Wymagania wstępne

W obszarze roboczym Zarządzanie funkcjami włącz następujące funkcję **Chronologiczne numerowanie**: Aby uzyskać więcej informacji, zapoznaj się z tematem [Zarządzanie funkcjami — omówienie](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="configure-chronological-numbering"></a>Konfiguruj numerowanie chronologiczne

Numeracja chronologicznej wpływa na następujące dokumenty.

**Rozrachunki z odbiorcami**
- Faktura dla odbiorcy
- Załącznik faktury dla odbiorcy
- Faktura korygująca sprzedaży
- Załącznik faktury korygującej sprzedaży
- Faktura niezależna
- Załącznik faktury niezależnej
- Niezależna faktura korygująca
- Załącznik niezależnej faktury korygującej
- Dokument dostawy
- Załącznik dokumentu dostawy
- Załącznik korekty dokumentu dostawcy
- Załącznik noty odsetkowej
- Załącznik z ponagleniem

**Rozrachunki z dostawcami**
- Załącznik faktury
- Załącznik faktury korygującej
- Załącznik dokumentu przyjęcia produktów

**Zarządzanie projektami**
- Faktura VAT
- Załącznik faktury
- Faktura kredytowa
- Załącznik faktury korygującej 

### <a name="define-number-sequences"></a>Zdefiniuj sekwencje liczb

Aby zdefiniować sekwencje numerów, przejdź do **Administrowanie organizacją** > **Numery kolejne** > **Numery kolejne**. Można zdefiniować dowolną liczbę sekwencji numerów, aby objąć odpowiednie okresy dla wymaganych dokumentów. 

Określ firmę dla każdej sekwencji numerów. Segmenty ciągów liczbowych należy zdefiniować w taki sposób, aby zapewniały chronologiczną kolejność okresów. Na przykład nazwy segmentów mogą zawierać specjalny przedrostek identyfikujący określony okres.

![Ustawienia sekwencji numerów.](media/chrono-num-sequence.jpg)

### <a name="configure-number-sequence-groups"></a>Konfigurowanie sekwencji identyfikatorów grup

Aby skonfigurować grupy sekwencji numerów, przejdź do **Rozrachunki z odbiorcami** > **Konfiguracja** > **Parametry modułu rozrachunków z odbiorcami**. Na karcie **Sekwencje numerów** zdefiniuj wymaganą liczbę grup sekwencji numerów, aby pokryć koszty określonej liczby okresów. 

Dla każdej grupy w sekcji **Odwołanie** wybierz jedno z obsługiwanych odwołań do dokumentów, a w polu **Kod sekwencji numerów** odwołaj się do sekwencji numerów utworzonej wcześniej dla powiązanego okresu.

![Ustawienia grupy sekwencji numerów.](media/chrono-num-sequence-group.jpg)

Podobnie skonfiguruj grupy sekwencji numerów w modułach **Rozrachunki z dostawcami** oraz **Zarządzanie projektami i ich księgowanie**.

### <a name="configure-number-sequence-groups-chronology"></a>Skonfiguruj chronologię grup sekwencji numerów

Aby skonfigurować chronologicznie grupy sekwencji numerów, przejdź do **Administrowanie organizacją** > **Numery kolejne** > **Chronologiczne grupy sekwencji liczb**. Zdefiniuj warunki możliwości zastosowania dla grup sekwencji numerów.

![Ustawienia numerów chronologicznych.](media/chrono-num-sequence-group-period.jpg)

| Pole            | opis                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Weszła w życie  | Data rozpoczęcia obowiązywania grupy sekwencji numerów. |
| Data ważności      | Data zakończenia obowiązywania grupy sekwencji numerów. Jeśli data zakończenia nie zostanie zastosowana, wybierz opcję **Nigdy**. |
| Grupa sekwencji numerów | Grupa sekwencji numerów, która będzie używana do generowania numerów dokumentów w okresie. |
| Oryginalna grupa sekwencji numerów | Ten kod grupy sekwencji numerów jest używany do dodatkowego filtrowania w przypadkach, gdy dokumenty mają już przypisaną określoną *stałą* grupę numerów. Wartość pusta jest uważana za określoną wartość. Jeśli chcesz zignorować wstępnie przypisaną grupę, użyj opcji **Domyślna** dla tej konfiguracji. |
| Domyślna | Jeśli ta opcja jest włączona, system ignoruje wstępnie przypisaną grupę numerów dokumentów i wykorzystuje tylko daty rozpoczęcia i zakończenia okresów do analizy stosowalności. Jeśli ten tryb jest wyłączony, do wyboru jest używana pełna kombinacja **Data wprowadzenia** + **Data ważności** + **Oryginalna grupa sekwencji numerów**. |

## <a name="document-posting"></a>Księgowanie dokumentów
Podczas księgowania dokumentu odpowiednia grupa numerów jest przypisywana do dokumentu na podstawie daty księgowania dokumentu, a następnie używana do generowania numeru dokumentu na podstawie wykrytej sekwencji numerów. System wyświetla komunikat dotyczący przypisania grup sekwencji numerów.

![Numer dokumentu.](media/chrono-num-sequence-fti.jpg)

> [!NOTE]
> W niektórych krajach zaimplementowano już określoną logikę numeracji dokumentów. W tym przypadku logika specyficzna dla kraju zastąpi funkcję **Numerowania chronologicznego**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
