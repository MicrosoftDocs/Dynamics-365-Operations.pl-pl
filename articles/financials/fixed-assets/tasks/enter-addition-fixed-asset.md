---
title: Wprowadzanie środka komplementarnego dla środka trwałego
description: W tej procedurze pokazano, jak dodać środek komplementarny do istniejącego środka trwałego.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetAddition
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3c9733f07f995dd37669f3c33fd0f082daa34dd2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566945"
---
# <a name="enter-an-addition-to-a-fixed-asset"></a>Wprowadzanie środka komplementarnego dla środka trwałego

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano, jak dodać środek komplementarny do istniejącego środka trwałego. Celem komplementarnych środków trwałych jest śledzenie wzbogacania, konserwacji lub ulepszeń składników aktywów. Służą one wyłącznie do celów informacyjnych. Wszelkie zmiany wartości lub okresu użytkowania środka trwałego należy wprowadzać osobno.   



Procedura korzysta z roli Księgowy i danych firmy demonstracyjnej USMF.

1. Przejdź do Środki trwałe > Środki trwałe > Środki trwałe.
2. Na liście odszukaj i zaznacz środek trwały, do którego ma zostać dodany środek komplementarny.
3. Na liście kliknij łącze w wybranym wierszu.
4. W okienku akcji kliknij pozycję Środek trwały.
5. Kliknij opcję Komplementarne środki trwałe.
6. Kliknij przycisk Nowy.
7. W polu Nazwa wpisz wartość.
8. Ustaw datę zakupu środka komplementarnego lub rozpoczęcia jego użytkowania.
9. Wprowadź koszt towaru albo informacje o jego konserwacji lub ulepszeniach.
10. Wprowadź liczbę w polu Ilość.
    * Łączny koszt nie ma wpływu na wartość środka trwałego i służy tylko do celów śledzenia i informacyjnych. Jeśli koszt będzie kapitalizowany, należy osobno zaksięgować transakcję zwiększenia wartości.  
11. Kliknij kartę Ogólne.
    * Zaznacz opcję Zwiększa okres użytkowania, jeśli środek komplementarny wydłuża okres użytkowania składnika aktywów.  
    * To pole służy wyłącznie do celów informacyjnych. W celu przedłużenia okresu użytkowania zmodyfikuj go w modelach ewidencji i/lub księgach amortyzacji składnika aktywów.  

