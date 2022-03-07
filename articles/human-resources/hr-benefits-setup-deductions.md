---
title: Konfigurowanie potrąceń
description: Funkcja potrąceń w programie Microsoft Dynamics 365 Human Resources pozwala określić, ile (jeśli w ogóle) należy potrącić z wynagrodzenia pracownika na każde świadczenie.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a865f109379064ae8829532af9253238e203c322
ms.sourcegitcommit: 8592c661b41f9cef8b7ef2863a3b97bf49a4e6f9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/26/2021
ms.locfileid: "7423504"
---
# <a name="configure-deductions"></a>Konfigurowanie potrąceń

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Funkcja potrąceń w programie Microsoft Dynamics 365 Human Resources pozwala określić, ile (jeśli w ogóle) należy potrącić z wynagrodzenia pracownika na każde świadczenie. Potrącenia mają daty obowiązywania, więc można prowadzić historyczny rejestr informacji o potrąceniach. 

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Potrącenia**.

2. Wybierz pozycję **Nowy**.

3. Określ wartości dla następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Potrącenie** | Unikatowy identyfikator używany do identyfikowania potrącenia na świadczenie. |
   | **Opis** | Opis potrącenia. |
   | **Weszła w życie** | Data rozpoczęcia. Domyślną wartością jest bieżąca data systemu. |
   | **Data ważności** | Data zakończenia. Wartość domyślna to 31.12.2154, czyli nigdy. |
   | **Nagłówek** | Kod nagłówka z systemu listy płac, który będzie używany przez to potrącenie dla części potrącenia opłacanej przez pracownika podczas przetwarzania świadczeń dla listy płac. Jest używany w przypadku korzystania z zewnętrznego dostawcy listy płac. |
   | **Odwołanie do potrącenia dla listy płac pracownika etatowego** | Kod potrącenia z systemu listy płac, którego to potrącenie będzie używane dla pracownika etatowego w części jego potrącenia podczas przetwarzania świadczeń dla listy płac. |
   | **Nagłówek kwoty** | Kod nagłówka z systemu listy płac, który będzie używany przez tę kwotę potrącenia dla części potrącenia opłacanej przez pracownika podczas przetwarzania świadczeń dla listy płac. Zwykle jest używany w przypadku korzystania z zewnętrznego dostawcy listy płac. |
   | **Można usunąć** | Określa, czy wartość wyeksportowana z programu Dynamics 365 for Finance and Operations może powodować usunięcie wartości w systemie listy płac. |
   | **Kolumny sparowane** | Określa, czy nagłówek i kwota potrącenia mają być eksportowane w sparowanych sąsiadujących kolumnach do systemu listy płac. |
   | **Zmień datę wejścia w życie** | Dzień, w którym zmiana potrącenia na świadczenie wejdzie w życie. W tym dniu jest zmieniane potrącenie na świadczenie i są aktualizowane wszystkie plany świadczeń skojarzone z tym potrąceniem, jeśli zostanie uruchomione przetwarzanie **Aktualizacja zmiany potrącenia**. |
   | **Zakończono zmianę potrącenia** | Pole wyboru **Zakończono zmianę potrącenia** zostanie automatycznie zaznaczone, gdy proces przetwarzania aktualizacji zmiany potrącenia wprowadzi wszystkie zmiany w potrąceniach na świadczenia. |
   
4. Aby śledzić zmiany konfiguracji stawki świadczenia i nimi zarządzać, wybierz opcję **Akcje**, a następnie wybierz opcję **Obsługuj wersje**.

5. Wybierz opcję **Zapisz**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
