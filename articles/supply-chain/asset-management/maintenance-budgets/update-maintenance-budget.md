---
title: Aktualizowanie budżetu konserwacji
description: W tym temacie wyjaśniono, jak aktualizować budżet konserwacji w zarządzaniu składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e43abd4644eec8c91606ec48bbecf30f12600856
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435286"
---
# <a name="update-maintenance-budgets"></a>Aktualizowanie budżetu konserwacji

[!include [banner](../../includes/banner.md)]

 

Na stronie **Wiersze budżetu konserwacji** są wyświetlane wszystkie wiersze budżetu, które zostały utworzone dla budżetu wybranego na stronie **Budżety konserwacji**. (Aby uzyskać więcej informacji, przejrzyj temat [Tworzenie budżetu konserwacji](create-maintenance-budget.md)) wiersze budżetu konserwacji można ponownie obliczyć i skorygować do momentu zatwierdzenia budżetu konserwacji. Po upływie okresu budżetu i zaksięgowaniu kosztów w module Zarządzanie składnikami majątku można również zaktualizować wiersze budżetu o koszty rzeczywiste.

## <a name="recalculate-a-maintenance-budget"></a>Oblicz ponownie budżet konserwacji

Budżet obsługi można ponownie obliczyć na stronie **Wiersze budżetu konserwacji**. Podczas ponownego obliczania budżetu obsługi są usuwane istniejące wiersze budżetu i wykonywane jest nowe obliczanie.

1. Na stronie **Wiersze budżetu konserwacji** wybierz opcję **Oblicz ponownie.**
2. W oknie dialogowym **Ponowne obliczanie** budżetu wprowadź wymagane zmiany w nowych obliczeniach, a następnie kliknij **OK**.

Nowe wiersze budżetu są tworzone zgodnie z ustawionymi wartościami.

## <a name="adjust-budget-lines"></a>Korygowanie wierszy budżetu

Zamiast ponownego obliczania całego budżetu konserwacji można skorygować wybrane wiersze związane z kosztami budżetowymi.

1. Na stronie **Wiersze budżetu konserwacji** wybierz wiersze, dla których ma zostać zaktualizowany koszt budżetowy.
2. Wybierz **Dostosuj**.
3. Aby dodać kwotę do wybranych wierszy, zaznacz pole wyboru **Dodaj koszt**, a następnie wprowadź wartość w polu **Dodaj wartość**.
4. Aby pomnożyć koszt budżetowy w wybranych wierszach budżetu przez współczynnik, zaznacz pole wyboru **pomnóż koszt** i wprowadź współczynnik w polu **mnożenie wartości**.

    Jeśli na przykład w polu **mnożenie wartości** wprowadzono wartość **1,2** koszt budżetowy zostanie zwiększony w wybranych wierszach o 20 procent. W przypadku wprowadzenia wartości **0,7** koszt budżetowy jest redukowany w wybranych wierszach o 30 procent.

5. Kliknij przycisk **OK**.

Wybrane wiersze budżetu są aktualizowane zgodnie z wartościami określonymi w kroku 3 lub 4.

## <a name="update-actual-costs"></a>Aktualizuj koszty rzeczywiste

Po upływie dat w wierszach budżetu i zaksięgowaniu kosztów rzeczywistych w module Zarządzanie składnikami majątku można również zaktualizować wiersze budżetu o koszty rzeczywiste.

1. Na stronie **Wiersze budżetu konserwacji** wybierz opcję **Aktualizuj koszt**.
2. W oknie dialogowym **Oblicz rzeczywisty koszt** wybierz opcję **OK**.

Pola **koszt rzeczywisty** w wierszach budżetu są aktualizowane, jeśli koszty rzeczywiste zostały zaksięgowane. Nowe wiersze budżetu mogą zostać wygenerowane, jeśli zostały utworzone nowe typy środków od momentu utworzenia budżetu, oraz jeśli te typy środków trwałych zostały użyte w środkach trwałych, dla których zostały zaksięgowane i pokrewne koszty W nowych wierszach budżetu są wyświetlane tylko koszty rzeczywiste, ponieważ nie zostały dla nich obliczone koszty budżetowe.

> [!NOTE]
> Aby wyświetlić przegląd kosztów rzeczywistych podzielonych na koszty dodatkowe, korygujące i inwestycyjne, można wykonać obliczenia dla tego samego okresu na stronie **Formant kosztów składników majątku**. 

## <a name="manually-add-budget-lines"></a>Ręczne dodawanie wierszy planu budżetu

Na stronie **Wiersze budżetu konserwacji** można ręcznie dodać nowy wiersz budżetu, wybierając opcję **nowy**, a następnie dokonując wyboru w wierszu. Oto kilka przykładów sytuacji, w których takie rozwiązanie może być użyteczne:

- Wiadomo, że odnawianiem niektórych środków trwałych znajduje się obecnie w fazie planowania, ale powiązane zadania nie zostały jeszcze utworzone w module Zarządzanie składnikami majątku. Należy jednak uwzględnić koszty budżetowe tych zadań, które mają być uwzględnione w budżecie konserwacji.
- Nowe środki trwałe lub typy środków zostały utworzone od czasu dokonania budżetu konserwacji, ale nie skonfigurowano jeszcze planów konserwacji dla tych składników lub typów składników majątku. Należy jednak uwzględnić koszty budżetowe tych składników majątku, które mają być uwzględnione w budżecie konserwacji.
