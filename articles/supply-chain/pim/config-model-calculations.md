---
title: Obliczenia na potrzeby modelu konfiguracji produktu
description: W tym temacie opisano sposób tworzenia obliczeń dla atrybutów w modelu konfiguracji produktu
author: t-benebo
ms.date: 03/18/2021
ms.topic: article
ms.search.form: PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-18
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eaf6264f060d33575740ad38e7a65158baba296b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829625"
---
# <a name="product-configuration-model-calculations"></a>Obliczenia na potrzeby modelu konfiguracji produktu

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób tworzenia obliczeń dla atrybutów w modelu konfiguracji produktu.

## <a name="prerequisites"></a>Wymagania wstępne

Obliczeń są używane w modelu konfiguracji produktu do obliczania wartości konfiguracji produktu. Aby można było rozpocząć konfigurowanie obliczeń, musi istnieć powiązany model konfiguracji produktu. Aby uzyskać przegląd procesu konfiguracji dla modeli konfiguracji i powiązanych zadań, zobacz temat [Konfigurowanie modelu konfiguracji produktu](set-up-maintain-product-configuration-model.md).

## <a name="create-a-calculation"></a>Tworzenie obliczenia

Obliczenie składa się z wyrażenia i atrybutu docelowego. Aby uzyskać więcej informacji, zobacz [Obliczenia dla modeli produktu w konfiguracji — często zadawane pytania](calculate-product-configuration-models.md).

Aby utworzyć obliczenie dla istniejącego modelu produktu, wykonaj następujące czynności.

1. Kliknij kolejno opcje **Zarządzanie informacjami o produktach \> Wspólne \> Modele konfiguracji produktu**.
1. Otwórz model konfiguracji produktu, a następnie kliknij przycisk **Edycja**.
1. Na skróconej karcie **Obliczenia** wybierz opcję **Dodaj**, aby dodać obliczenia, a następnie określ dla niego następujące pola:

    - **Nazwa** – wprowadź nazwę dla obliczeń.
    - **Opis** – wprowadź opis obliczeń.
    - **Atrybut docelowy** – wybierz atrybut, dla których są wykonywane obliczenia.

1. Wybierz polecenie **Edytuj wyrażenie**.
1. W oknie dialogowym **Wprowadzanie obliczenia** dodaj do wyrażenia wymagane atrybuty, operatory i wartości. Aby uzyskać więcej informacji o tym, jak pracować z tymi elementami, zobacz temat [Ograniczenia wyrażenia i ograniczenia tabeli w modelach konfiguracji produktu](expression-constraints-table-constraints-product-configuration-models.md).
1. Gdy wyrażenie jest gotowe, wybierz przycisk **OK**.

## <a name="calculation-examples"></a>Przykłady obliczeń

Ta sekcja zawiera kilka przykładów, które pokazują pracę obliczeń.

### <a name="example-1"></a>Przykład 1

Atrybutem docelowym jest wartość logiczna, a obliczenia wykorzystują następujące wyrażenie warunkowe:

`If[(decimalAttribute1 / decimalAttribute2) < 1, True, False]`

To wyrażenie zwróci wartość *Prawda* (True) do atrybutu docelowego, jeśli dziesiętny atrybut `decimalAttribute2` jest większy niż lub równy dziesiętnemu atrybutowi `decimalAttribute1`. W przeciwnym wypadku zwraca ona wartość logiczną *Fałsz* (False).

### <a name="example-2"></a>Przykład 2

W tym przykładzie jako atrybut docelowy jest używany atrybut tekstowy `textFixedList`. Ten atrybut zawiera następującą stałą listę.

| Wartość | Wartość zmiennej |
|---|---|
| A | 1a |
| mld | 2b |
| C | 2c |

Poniższy zrzut ekranu pokazuje, jak ustawienia tego atrybutu mogą wyglądać w systemie.

![Ustawienia typu atrybutu dla przykładu 2](media/model-calculations-example2.png "Ustawienia typu atrybutu dla przykładu 2")

Atrybut jest używany w następującym oświadczeniu warunkowym:

`If[integerAttribute < 150, 0, 2]`

Jeśli `integerAttribute` jest mniejszy niż 150, instrukcja zwraca wartość tekstową pierwszego rekordu na stałej liście, *A*. W przeciwnym razie zwraca wartość tekstową trzeciego rekordu na stałej liście, *C*.

> [!NOTE]
> Ustalona lista jest równoważna wyliczeniu od zera (wyliczeniu), a dostęp do jej wartości uzyskuje się za pomocą odpowiedniej liczby całkowitej. W związku z tym pierwsza stała wartość listy (*A*) zostanie dopasowana do wartości *0*, druga wartość (*B*) zostanie dopasowana do *1*, a trzecia wartość (*C*) zostanie dopasowana do *2*.

### <a name="example-3"></a>Przykład 3

W tym przykładzie zastosowano atrybut docelowy `textFixedList` z poprzedniego przykładu. Używa również innego atrybutu tekstowego `textAttribute`, który zawiera następującą stałą listę.

| Wartość | Wartość zmiennej |
|---|---|
| AA | 1aa |
| BB | 2bb |

Poniższy zrzut ekranu pokazuje, jak ustawienia tego atrybutu mogą wyglądać w systemie.

![Ustawienia typu atrybutu dla przykładu 3](media/model-calculations-example3.png "Ustawienia typu atrybutu dla przykładu 3")

Wartość atrybutu `textFixedList` jest obliczana przy użyciu następującego zestawienia warunkowego:

`If[textAttribute == "1aa", 0, 2]`

Jeśli wartość `textAttribute` ma wartość zmiennej równą *1aa*,, to wyrażenie zwraca wartość tekstową pierwszego rekordu na stałej liście `textFixedList`, *A*. W przeciwnym razie zwraca wartość tekstową trzeciego rekordu na stałej liście `textFixedList`, *C*.

> [!NOTE]
> - Instrukcja warunkowa musi korzystać z wartości zmiennej atrybutu.
> - W obliczeniach mogą być używane tylko atrybuty tekstu stałej listy.

## <a name="see-also"></a>Informacje dodatkowe

- [Obliczenia dla modeli produktu w konfiguracji — często zadawane pytania](calculate-product-configuration-models.md)
- [Dodawanie ograniczenia wyrażenia do modelu konfiguracji produktu](tasks/add-expression-constraint-product-configuration-model.md)
- [Omówienie modeli konfiguracji produktu](product-configuration-models.md)
