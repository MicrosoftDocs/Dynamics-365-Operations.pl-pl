---
title: Konfigurowanie parametrów zarządzania świadczeniami w firmie
description: Skonfiguruj parametry obszaru roboczego Zarządzanie świadczeniami w firmie dostępnego w programie Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 87d4f1e7580b333fd17d3b779aafa47c5baed424
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805665"
---
# <a name="configure-benefits-management-parameters-per-company"></a>Konfigurowanie parametrów zarządzania świadczeniami w firmie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dla każdej organizacji oferującej świadczenia należy skonfigurować ustawienia wiadomości e-mail z potwierdzeniem świadczeń.

## <a name="configure-confirmation-email-settings"></a>Konfigurowanie ustawień wiadomości e-mail z potwierdzeniem

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry Human Resources**.

2. Na karcie **Zarządzanie świadczeniami** wprowadź wartości w następujących polach: 

   | Pole | opis |
   | --- | --- |
   | **Wyślij wiadomość e-mail z potwierdzeniem** | Gdy ta funkcja jest włączona, do pracowników etatowych wysyłana jest wiadomość e-mail z potwierdzeniem, gdy zarejestrują się na świadczenia w obszarze Samoobsługa pracownika etatowego. |
   | **Szablon wiadomości e-mail z potwierdzeniem** | Wybierz szablon e-mail organizacji, który ma być stosowany podczas wysyłania potwierdzenia rejestracji. Jeśli nie wybierzesz szablonu, zostanie wysłana następująca ogólna wiadomość e-mail:<br><br>%EmployeeFirstName%.<br><br>Gratulacje! Twoja rejestracja na świadczenia została pomyślnie zakończona.<br><br>Dziękujemy,<br>Świadczenia w firmie <Company/Org name>. |
   | **Domyślny adres e-mail nadawcy** | Adres e-mail, który ma być użyty do wysłania wiadomości e-mail z potwierdzeniem. |

3. Wybierz opcję **Zapisz**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]