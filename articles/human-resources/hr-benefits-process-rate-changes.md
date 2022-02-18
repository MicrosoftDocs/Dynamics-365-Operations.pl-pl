---
title: Przetwarzanie zmian stawek
description: W tym temacie opisano sposób przetwarzania zdarzeń zmiany stawki świadczenia w programie Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitRate, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5e0dfbdde8ee950a0341fffb1e268fff05434953
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070382"
---
# <a name="process-rate-changes"></a>Przetwarzanie zmian stawek


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie wyjaśniono sposób przetwarzania zmian stawki świadczenia w Microsoft Dynamics 365 Human Resources, gdy nowy lub istniejący plan świadczeń ma zmianę w ustawieniach reguły uprawnienia. Jeśli Nowa reguła uprawnienia zostanie utworzona i przypisana do planu, system wyświetli monit o ponowne przetworzenie pracownika, aby sprawdzić, czy pracownicy mogą obecnie kwalifikować się do planu na podstawie nowych opcji dotyczących uprawnień. 

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Przetwarzanie** wybierz opcję **Przetwarzanie aktualizacji zmiany stawki**.

2. W oknie dialogowym **Uruchamianie procesu aktualizacji stawki świadczenia** określ wartości następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Okres rejestracji** | Okres rejestracji służący do przetworzenia zmian stawki. |

3. Jeśli chcesz uruchomić ten proces w tle, wybierz opcję **Uruchom w tle** i wykonaj następujące czynności:

   1. Umożliwia wprowadzanie informacji o przetwarzaniu.

   2. Aby skonfigurować zadanie cykliczne, wybierz opcję **cykl**, wprowadź informacje o cyklu i wybierz **OK**.

   3. Aby skonfigurować alert zadania, wybierz **alerty**, wybierz alerty do odebrania, a następnie kliknij przycisk **OK**.

   4. Kliknij przycisk **OK**. Proces będzie uruchamiany z parametrami określonymi przez użytkownika.

4. Kliknij przycisk **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
