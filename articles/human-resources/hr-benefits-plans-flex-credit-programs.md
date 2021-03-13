---
title: Konfigurowanie programów kredytu elastycznego
description: Za pomocą programów kredytu elastycznego w programie Microsoft Dynamics 365 Human Resources można rejestrować pracowników na świadczenia zgodnie z ustaloną wcześniej liczbą elastycznych punktów kredytowych.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitCreditPrograms, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f701d9e38e04769f1255e6f8cb3ee757bf22f96c
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113894"
---
# <a name="set-up-flex-credit-programs"></a>Konfigurowanie programów kredytu elastycznego

Za pomocą programów kredytu elastycznego w programie Microsoft Dynamics 365 Human Resources można rejestrować pracowników na świadczenia zgodnie z ustaloną wcześniej liczbą elastycznych punktów kredytowych. Pracownicy mogą wybrać sposób przydzielania ich elastycznych punktów kredytowych. Na przykład jeśli pracownik jest objęty planem ubezpieczenia zdrowotnego swojego małżonka, może chcieć wykorzystać punkty kredytowe, które normalnie przeznaczyłby na ubezpieczenie zdrowotne, na inne świadczenia. 

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Plany** wybierz opcję **Programy kredytu elastycznego**.

2. Wybierz pozycję **Nowy**.

3. Określ wartości dla następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Identyfikator kredytu świadczenia** | Unikatowy identyfikator programu kredytu elastycznego. |
   | **Opis** | Opis programu kredytu elastycznego. | 
   | **Data Od** | Data i godzina aktywacji programu kredytu elastycznego. |
   | **Data Do** | Data i godzina zakończenia działania programu kredytu elastycznego. Można pozostawić wartość domyślną (31.12.2154), aby wskazać, że program kredytu elastycznego nie ma zaplanowanego okresu ważności. |
   | **Suma wartości kredytu** | Liczba punktów kredytowych, jakie będzie miał każdy pracownik na swoje świadczenia. |
   | **Reguła naliczania proporcjonalnego** | Reguła używana do proporcjonalnego obliczania liczby elastycznych punktów kredytowych, gdy pracownik zostanie zatrudniony w trakcie okresu wykorzystywania elastycznych punktów kredytowych. </br></br><ul><li>**Brak** — pracownik nie otrzymuje żadnych elastycznych punktów kredytowych, jeśli zostanie zatrudniony po rozpoczęciu okresu programu kredytu elastycznego.</li><li>**Pełny kredyt** — pracownik otrzymuje pełną liczbę elastycznych punktów kredytowych, niezależnie od momentu, w którym został zatrudniony.</li><li>**Naliczanie proporcjonalne** — pracownik otrzymuje liczbę elastycznych punktów kredytowych proporcjonalną do daty rozpoczęcia zatrudnienia.</li></ul> |
   | **Formuła naliczania proporcjonalnego kredytu elastycznego** | Reguła używana do proporcjonalnego obliczania liczby elastycznych punktów kredytowych dla pracowników, którzy zostali zatrudnieni w trakcie okresu świadczeniowego zdefiniowanego w programie kredytu elastycznego. Naliczanie proporcjonalne jest oparte na dacie rozpoczęcia zatrudnienia. To pole jest używane tylko w przypadku zaznaczenia wartości **Naliczanie proporcjonalne** w polu **Reguła naliczania proporcjonalnego**. </br></br><ul><li>**Dziennie** — liczba elastycznych kredytów, które pracownik otrzymuje, odnosi się do poziomu dni. Łączna liczba elastycznych punktów kredytowych jest dzielona przez liczbę dni w okresie. Jeśli na przykład okres świadczeniowy wynosi 400 dni, system podzieli łączną liczbę elastycznych punktów kredytowych przez 400 w celu obliczenia liczby elastycznych punktów kredytowych, jaką pracownicy otrzymują na dzień.</li><li>**Bieżący miesiąc** — liczba elastycznych kredytów, które pracownik otrzymuje, odnosi się do poziomu miesięcy, z zaokrągleniem do bieżącego miesiąca. Łączna liczba elastycznych punktów kredytowych jest dzielona przez liczbę miesięcy w okresie. Jeśli na przykład okres świadczeniowy wynosi 15 miesięcy, system podzieli łączną liczbę elastycznych punktów kredytowych przez 15 w celu obliczenia liczby elastycznych punktów kredytowych, jaką pracownicy otrzymują na miesiąc.</li><li>**Następny miesiąc** — liczba elastycznych kredytów, które pracownik otrzymuje, odnosi się do poziomu miesięcy, z zaokrągleniem do następnego miesiąca. Łączna liczba elastycznych punktów kredytowych jest dzielona przez liczbę miesięcy w okresie. Jeśli na przykład okres świadczeniowy wynosi 15 miesięcy, system podzieli łączną liczbę elastycznych punktów kredytowych przez 15 w celu obliczenia liczby elastycznych punktów kredytowych, jaką pracownicy otrzymują na miesiąc.</li></ul> |
   
