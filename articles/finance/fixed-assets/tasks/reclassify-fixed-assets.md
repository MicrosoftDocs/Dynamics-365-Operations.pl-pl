---
title: Zmień klasyfikację środków trwałych
description: W tym artykule wyjaśniono proces przeklasyfikowania środków trwałych. Aby przeklasyfikować środek trwały, należy przenieść go do nowej grupy środków trwałych lub przypisać mu nowy numer środka trwałego w tej samej grupie.
author: moaamer
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 89c046b131afd1728b26465816eee98ee1898e49
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861395"
---
# <a name="reclassify-fixed-assets"></a>Zmień klasyfikację środków trwałych

[!include [banner](../../includes/banner.md)]

Aby przeklasyfikować środek trwały, należy przenieść go do nowej grupy środków trwałych lub przypisać mu nowy numer środka trwałego w tej samej grupie. 

Po przeklasyfikowaniu środka trwałego:

- Wszystkie księgi dla istniejącego środka trwałego zostają utworzone dla nowego środka trwałego. Wszystkie informacje skonfigurowane dla oryginalnego środka trwałego zostają skopiowane do nowego środka stałego. Stan ksiąg oryginalnego środka trwałego zostaje ustawiony na Zamknięte. 

- Nowe księgi nowego środka stałego zawierają datę przeklasyfikowania w polu **Data nabycia**. Data w polu **Data rozpoczęcia amortyzacji** jest kopiowana z oryginalnych informacji o środku trwałym. Jeśli amortyzacja jest już rozpoczęta, to w polu **Data ostatniego uruchomienia amortyzacji** zostaje wyświetlona data przeklasyfikowania. 

- Transakcje istniejącego środka trwałego zostają anulowane i wygenerowane ponownie dla nowego środka trwałego.

- W przypadku przeklasyfikowania środka trwałego z transakcją przeniesienia w **centrum akcji** zostanie wyświetlony komunikat informujący, że transakcja przeniesienia nie została zakończona w trakcie procesu przeklasyfikowania. Konieczne jest zakończenie transakcji przeniesienia w celu przeniesienia istniejących transakcji przeklasyfikowania do odpowiednich wymiarów finansowych. 

   W procesie przeklasyfikowania system uruchamia następujące akcje w celu przeklasyfikowania salda środków trwałych z oryginalnego środka trwałego do nowego środka trwałego. 
   
   - Proces przeklasyfikowania kopiuje dane z oryginalnej księgi środków trwałych do nowej księgi środków trwałych.

   - Transakcja przeklasyfikowania wykorzystuje informacje z oryginalnego zaksięgowanego nabycia, które zawiera informacje o wymiarach finansowych zawartych w transakcji nabycia.  
   
   - Jednocześnie proces przeklasyfikowania wycofuje oryginalną transakcję nabycia i przeniesienia środka trwałego. 

Poniższy diagram i procedura stanowią przykład procesu przeklasyfikowania. 

[![Diagram pokazujący proces przeklasyfikowania.](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)

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
