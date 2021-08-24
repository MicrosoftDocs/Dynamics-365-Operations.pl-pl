---
title: Definiowanie punktów lojalnościowych
description: Ta procedura prowadzi przez definiowanie punktów lojalnościowych.
author: scott-tucker
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailLoyaltyRewardPoints
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 509db13f1bae9f41537a5d91aeba862ed2e4291d72739e83e22fb860791d6355
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738679"
---
# <a name="define-loyalty-reward-points"></a>Definiowanie punktów lojalnościowych

[!include [banner](../includes/banner.md)]

Ta procedura prowadzi przez definiowanie punktów lojalnościowych. Punkty lojalnościowe powinny być skonfigurowane przed skonfigurowaniem programu lojalnościowego. Procedura wykorzystuje dane firmy demonstracyjnej USRT.

1. Wybierz kolejno opcje Retail i Commerce > Odbiorcy > Lojalność > Punkty lojalnościowe.
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
    * Punkty lojalnościowe wygasają określoną liczbę dni, miesięcy lub lat po wydaniu. Wartość „0” oznacza, że punkty lojalnościowe nigdy nie wygasną.  
10. W polu Jednostka okresu ważności wybierz opcję.
11. Kliknij przycisk Zapisz.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]