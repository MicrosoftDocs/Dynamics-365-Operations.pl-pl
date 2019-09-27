---
title: Typy krytyczności składnika majątku
description: W tym temacie objaśniono typy krytyczności składników majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 660038060826ade9301e50143e49b53ba3fcd3ab
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783521"
---
# <a name="asset-criticalities"></a>Krytyczności składników majątku

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

W tym temacie objaśniono typy krytyczności składników majątku w module Zarządzanie składnikami majątku. Krytyczność składników majątku jest związana ze składnikami majątku i jest przenoszona do zleceń pracy. Nie można jej zmienić w zleceniu pracy. Krytyczność składników majątku jest używana do obliczania krytyczności zlecenia pracy podczas planowania zlecenia pracy. Innymi słowy, służy do obliczania stopnia, w jakim zadanie konserwacji składnika majątku wpływa na harmonogram produkcji i produktywność w firmie. Aby uzyskać więcej informacji na temat konfiguracji, która jest powiązana z obliczaniem oceny wyników dla planowania zlecenia pracy, zobacz temat [Parametry modułu Zarządzania składnikami majątku](../setup-for-objects/enterprise-asset-management-parameters.md).

Aby skonfigurować krytyczność, należy najpierw utworzyć typy krytyczności, które powinny być używane w ustawieniach składnika majątku. Następnie należy skonfigurować krytyczność składnika majątku.

## <a name="set-up-criticality-types"></a>Konfigurowanie typów krytyczności

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Składniki majątku** \> **Typy krytyczności**.
2. Wybierz **Nowy**, aby utworzyć rekord.
3. W polu **Krytyczność** wprowadź liczbę oznaczającą krytyczność.
4. W polu **Nazwa** wprowadź nazwę typu krytyczności.
5. W polu **Współczynnik** wpisz współczynnik. Ten współczynnik jest używany podczas obliczania planowania zleceń pracy w celu określenia rekordu krytyczności, który ma zostać użyty. (Zawsze jest używany rekord o najwyższym współczynniku). To ustawienie ma zastosowanie, jeśli, jak to pokazano na poniższej ilustracji, zostaną utworzone wiersze krytyczności, które mają taką samą wartość krytyczności.

    ![Rysunek 1](media/23-setup-for-objects.png)

## <a name="set-up-asset-criticalities"></a>Konfigurowanie krytyczności składników majątku

1. Wybierz kolejno **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Krytyczności składnika majątku**.
2. Wybierz **Nowy**, aby utworzyć rekord.
3. W zależności od wymaganego poziomu szczegółowości krytyczności składnika majątku dokonaj odpowiednich selekcji w polach **Lokalizacja czynności konserwacyjnych**, **Typ składnika majątku**, **Producent** **Model**, **Składnik majątku**, **Kategoria typu zadania**, **Typ zadania**, **Wariant typu zadania** oraz **Kryterium doboru**.

    > [!NOTE]
    > Kiedy krytyczność składnika majątku jest wybrana, moduł Zarządzanie składnikami majątku przechodzi przez wszystkie rekordy krytyczności składników majątku, szukając ewentualnego dopasowania. W pierwszej kolejności sprawdza zawsze kombinację najbardziej szczegółową. Innymi słowy, moduł Zarządzanie składnikami majątku najpierw sprawdza **Kryterium doboru**. Jeśli nie zostanie znaleziony żaden odpowiednik, sprawdza **Wariant typu zadania**. Jeśli nie zostanie znaleziony żaden odpowiednik, sprawdza **Typ zadania** itd. Jak widać w układzie strony to zachowanie oznacza, że aby znaleźć najbardziej konkretną kombinację, moduł Zarządzanie składnikami majątku sprawdza każdy rekord od prawej do lewej pod kątem dopasowania. Jeśli nie uda się znaleźć dopasowania, jest używany rekord „domyślny”, który nie ma zaznaczeń.

4. W polu **Krytyczność** wybierz jedną z wartości krytyczności utworzonych w poprzedniej procedurze.

### <a name="notes-about-criticality-setup"></a>Uwagi dotyczące konfiguracji krytyczności

- Jeśli w tej konfiguracji zmienisz krytyczność składnika majątku po użyciu go w jakimś zleceniu pracy, krytyczność na zleceniu pracy nie jest odpowiednio aktualizowana.
- Krytyczność na zleceniu pracy jest przeliczana za każdym razem, gdy wiersz zlecenia pracy jest dodawany lub usuwany ze zlecenia pracy.
- Jeśli zlecenie pracy zawiera kilka zadań pracy, najwyższy poziom krytyczności, zgodnie z polem **Współczynnik** na stronie **Typy krytyczności**, jest zawsze używana w zleceniu pracy.
- Ogólnie rzecz biorąc, krytyczność składników majątku można zmienić na przestrzeni czasu. Krytyczność może mieć wpływ na zakup nowego sprzętu, remonty i tak dalej. Rozważ ponowną ocenę krytyczności składników majątku w regularnych odstępach czasu (np. raz na rok lub co dwa lata), aby upewnić się, że definicje krytyczności odpowiadają aktualnej konfiguracji produkcji.