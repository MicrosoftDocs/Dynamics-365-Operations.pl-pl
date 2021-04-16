---
title: Zmień klasyfikację środków trwałych
description: Aby przeklasyfikować środek trwały, należy przenieść go do nowej grupy środków trwałych lub przypisać mu nowy numer środka trwałego w tej samej grupie.
author: saraschi2
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8935213c4629de408a48df5e54a2122324e1b3e7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823939"
---
# <a name="reclassify-fixed-assets"></a>Zmień klasyfikację środków trwałych

[!include [banner](../../includes/banner.md)]

Aby przeklasyfikować środek trwały, należy przenieść go do nowej grupy środków trwałych lub przypisać mu nowy numer środka trwałego w tej samej grupie. 

Po przeklasyfikowaniu środka trwałego:

* Wszystkie księgi dla istniejącego środka trwałego zostają utworzone dla nowego środka trwałego. Wszystkie informacje skonfigurowane dla oryginalnego środka trwałego zostają skopiowane do nowego środka stałego. Stan ksiąg oryginalnego środka trwałego zostaje ustawiony na Zamknięte. 

* Nowe księgi nowego środka stałego zawierają datę przeklasyfikowania w polu **Data nabycia**. Data w polu **Data rozpoczęcia amortyzacji** jest kopiowana z oryginalnych informacji o środku trwałym. Jeśli amortyzacja jest już rozpoczęta, to w polu **Data ostatniego uruchomienia amortyzacji** zostaje wyświetlona data przeklasyfikowania. 

* Transakcje istniejącego środka trwałego zostają anulowane i wygenerowane ponownie dla nowego środka trwałego.

Aby przeklasyfikować środek trwały, należy wykonać następujące kroki:

1. Wybierz kolejno opcje **Środki trwałe > Zadania okresowe > Przeklasyfikowanie**.
2. W polu **Grupa środków trwałych** zaznacz grupę, którą chcesz przeklasyfikować.
3. W polu **Numer środka trwałego** zaznacz środek trwały, który chcesz przeklasyfikować.
4. W polu **Nowa grupa środków trwałych** wybierz grupę, do której ma zostać przeniesiony środek trwały.
    * Jeśli nowa grupa środków trwałych jest przypisana do numeracji, pole **Nowy numer środka trwałego** zostanie zaktualizowane o numer z nowej numeracji grupy środków trwałych. W przeciwnym razie pole **Nowy numer środka trwałego** jest aktualizowane o numer z numeracji ustawionej na stronie **Parametry środków trwałych**. Jeśli na stronie **Parametry środków trwałych** nie skonfigurowano numeracji, wpisz numer w polu **Nowy numer środka trwałego**.  
5. W polu **Data przeklasyfikowania** wprowadź datę.
6. W polu **Seria załączników** wprowadź lub wybierz wartość.
7. Kliknij przycisk **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]