---
title: Konfigurowanie parametrów zarządzania świadczeniami w firmie
description: W tym temacie opisano sposób konfigurowania parametrów zarządzania świadczeniami w firmie w programie Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 8/24/2021
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
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2d0bc8d511126901be09028dc3c10636f2902e79
ms.sourcegitcommit: 8592c661b41f9cef8b7ef2863a3b97bf49a4e6f9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/26/2021
ms.locfileid: "7423312"
---
# <a name="configure-benefits-management-parameters-per-company"></a>Konfigurowanie parametrów zarządzania świadczeniami w firmie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dla każdej organizacji oferującej świadczenia należy skonfigurować ustawienia wiadomości e-mail z potwierdzeniem świadczeń.

## <a name="configure-confirmation-email-settings"></a>Konfigurowanie ustawień wiadomości e-mail z potwierdzeniem

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry Human Resources**.

2. Na karcie **Zarządzanie świadczeniami** wprowadź wartości w następujących polach: 

   | Pole | opis |
   | --- | --- |
   | **Wyślij wiadomość e-mail z potwierdzeniem** | Gdy ta funkcja jest włączona, do pracowników etatowych wysyłana jest wiadomość e-mail z potwierdzeniem, gdy zarejestrują się na świadczenia w obszarze **Samoobsługa pracownika etatowego**. |
   | **Szablon wiadomości e-mail z potwierdzeniem** | Wybierz szablon e-mail organizacji, który ma być stosowany podczas wysyłania potwierdzenia rejestracji. Jeśli nie wybierzesz szablonu, zostanie wysłana następująca ogólna wiadomość e-mail:<br><br>%EmployeeFirstName%.<br><br>Gratulacje! Twoja rejestracja na świadczenia została pomyślnie zakończona.<br><br>Dziękujemy,<br>Świadczenia w firmie <Company/Org name>. |
   | **Domyślny adres e-mail nadawcy** | Adres e-mail, który ma być użyty do wysłania wiadomości e-mail z potwierdzeniem. |

3. Wybierz opcję **Zapisz**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
