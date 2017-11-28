--- 
title: "Zmień klasyfikację środków trwałych"
description: "Aby przeklasyfikować środek trwały, należy przenieść go do nowej grupy środków trwałych lub przypisać mu nowy numer środka trwałego w tej samej grupie."
author: saraschi2
manager: AnnBe
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cafd499e849570cae7b7f58bf2d487a7ac0093e6
ms.openlocfilehash: 6bce294329c7ec6dc436c3d3baf6597e0283c9bd
ms.contentlocale: pl-pl
ms.lasthandoff: 10/30/2017

---
# <a name="reclassify-fixed-assets"></a>Zmień klasyfikację środków trwałych

[!include[task guide banner](../../includes/task-guide-banner.md)]

Aby przeklasyfikować środek trwały, należy przenieść go do nowej grupy środków trwałych lub przypisać mu nowy numer środka trwałego w tej samej grupie. 

Po przeklasyfikowaniu środka trwałego:

• Wszystkie modele ewidencji istniejącego środka trwałego zostają utworzone dla nowego środka trwałego. Wszystkie informacje skonfigurowane dla oryginalnego środka trwałego zostają skopiowane do nowego środka stałego. Stan modeli ewidencji oryginalnego środka trwałego zostaje ustawiony na Zamknięte. 

• Nowe modele ewidencji nowego środka stałego zawierają datę przeklasyfikowania w polu Data nabycia. Data w polu Data rozpoczęcia amortyzacji jest kopiowana z oryginalnych informacji o środku trwałym. Jeśli amortyzacja jest już rozpoczęta, to w polu Data ostatniego uruchomienia amortyzacji zostaje wyświetlona data przeklasyfikowania. 

• Transakcje istniejącego środka trwałego zostają anulowane i wygenerowane ponownie dla nowego środka trwałego.

1. Wybierz kolejno opcje Środki trwałe > Zadania okresowe > Przeklasyfikowanie.
2. W polu Grupa środków trwałych zaznacz grupę, którą chcesz przeklasyfikować.
3. W polu Numer środka trwałego zaznacz środek trwały, który chcesz przeklasyfikować.
4. W polu Nowa grupa środków trwałych wybierz grupę, do której ma zostać przeniesiony środek trwały.
    * Jeśli nowa grupa środków trwałych jest przypisana do numeracji, pole Nowy numer środka trwałego zostanie zaktualizowane o numer z nowej numeracji grupy środków trwałych. W przeciwnym razie pole Nowy numer środka trwałego jest aktualizowane o numer z numeracji ustawionej na stronie Parametry środków trwałych. Jeśli na stronie Parametry środków trwałych nie skonfigurowano numeracji, wpisz numer w polu Nowy numer środka trwałego.  
5. W polu Data przeklasyfikowania wprowadź datę.
6. W polu Seria załączników wprowadź lub wybierz wartość.
7. Kliknij przycisk OK.


