---
title: Wprowadzanie środka komplementarnego dla środka trwałego
description: W tej procedurze pokazano, jak dodać środek komplementarny do istniejącego środka trwałego.
author: saraschi2
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetAddition
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 966fd191ad876aae86ff2511d6981b0437679becbe4984b087c1975dece351b6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742960"
---
# <a name="enter-an-addition-to-a-fixed-asset"></a>Wprowadzanie środka komplementarnego dla środka trwałego

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano, jak dodać środek komplementarny do istniejącego środka trwałego. Celem komplementarnych środków trwałych jest śledzenie wzbogacania, konserwacji lub ulepszeń składników aktywów. Służą one wyłącznie do celów informacyjnych. Wszelkie zmiany wartości lub okresu użytkowania środka trwałego należy wprowadzać osobno.   

Procedura korzysta z roli Księgowy i danych firmy demonstracyjnej USMF.

1. W okienku nawigacji przejdź do **Moduły > Środki trwałe > Środki trwałe > Środki trwałe**.
2. Na liście odszukaj i zaznacz środek trwały, do którego ma zostać dodany środek komplementarny.
3. Na liście kliknij łącze w wybranym wierszu.
4. W okienku akcji kliknij pozycję **Środek trwały**.
5. Kliknij opcję **Komplementarne środki trwałe**.
6. Kliknij przycisk **Nowy**.
7. W polu **Nazwa** wpisz wartość.
8. W polu **Data nabycia** ustaw datę zakupu dodatku lub usługi.
9. W polu **Koszt jednostkowy** wprowadź koszt towaru albo informacje o jego konserwacji lub ulepszeniach.
10. W polu **Ilość** wpisz liczbę. Łączny koszt nie ma wpływu na wartość środka trwałego i służy tylko do celów śledzenia i informacyjnych. Jeśli koszt będzie kapitalizowany, należy osobno zaksięgować transakcję zwiększenia wartości.  
11. Kliknij kartę **Ogólne**.

    * Zaznacz opcję **Zwiększa okres użytkowania** na **Tak**, jeśli środek komplementarny wydłuża okres użytkowania składnika aktywów.  
    * To pole służy wyłącznie do celów informacyjnych. W celu przedłużenia okresu użytkowania zmodyfikuj go w modelach ewidencji i/lub księgach amortyzacji składnika aktywów.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]