--- 
title: "Definiowanie punktów lojalnościowych"
description: "Ta procedura prowadzi przez definiowanie punktów lojalnościowych."
author: scott-tucker
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 05237a0ba3aa785432c8b1fc36284a47f9aabd4a
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="define-loyalty-reward-points"></a>Definiowanie punktów lojalnościowych

[!include[task guide banner](../includes/task-guide-banner.md)]

Ta procedura prowadzi przez definiowanie punktów lojalnościowych. Punkty lojalnościowe powinny być skonfigurowane przed skonfigurowaniem programu lojalnościowego. Procedura wykorzystuje dane firmy demonstracyjnej USRT.

1. Wybierz kolejno opcje Handel detaliczny i inny > Odbiorcy > Lojalność > Punkty lojalnościowe.
2. Kliknij przycisk Nowy.
3. W polu Identyfikator punktów lojalnościowych wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Typ punktów lojalnościowych wybierz opcję.
    * Zaznacz opcję Ilość, jeśli chcesz zaokrąglać punkty lojalnościowe do najbliższej liczby całkowitej. Zaznacz opcję Kwota, jeśli chcesz zaokrąglać punkty lojalnościowe według reguł zaokrąglania walut. W przypadku zaznaczenia opcji Ilość przejdź do następnego kroku tej procedury.  
6. W polu Waluta wpisz wartość.
    * Dla punktów lojalnościowych typu Kwota wszystkie przyznane punkty będą miały wybraną walutę. Do punktów lojalnościowych typu Ilość to pole nie ma zastosowania — pomiń ten krok.  
7. Zaznacz pole wyboru Można spieniężyć lub usuń jego zaznaczenie.
8. W polu Klasyfikacja spieniężeń wpisz liczbę.
    * Klasyfikacja spieniężeń jest używana, gdy co najmniej dwa wymienialne punkty lojalnościowe mogą zostać użyte do zapłaty za produkty. Jeśli dwa punkty lojalnościowe mają taką samą klasyfikację spieniężeń, zostanie użyty ten, który musi być wykorzystywany w mniejszej liczbie.  
9. W polu Wartość okresu ważności wprowadź lub wybierz wartość.
    * Punkty lojalnościowe wygasają określoną liczbę dni, miesięcy lub lat po wydaniu. Wartość „0” oznacza, że punkty lojalnościowe nigdy nie wygasają.  
10. W polu Jednostka okresu ważności wybierz opcję.
11. Kliknij przycisk Zapisz.


