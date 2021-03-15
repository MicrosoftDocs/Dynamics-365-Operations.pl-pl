---
title: Zmień klasyfikację środków trwałych
description: Aby przeklasyfikować środek trwały, należy przenieść go do nowej grupy środków trwałych lub przypisać mu nowy numer środka trwałego w tej samej grupie.
author: saraschi2
manager: AnnBe
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4cfc1425aca7a62205e0c7c50237f206a179a0e7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968861"
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