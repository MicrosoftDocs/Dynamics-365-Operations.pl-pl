---
title: Konfigurowanie parametrów zarządzania świadczeniami w firmie
description: Skonfiguruj parametry obszaru roboczego Zarządzanie świadczeniami w firmie dostępnego w programie Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 2943d0095e4c9421725b90e579b7cbb841038ab7
ms.sourcegitcommit: d02fae79d5c02a4bc4f4b16a410c2f5ce026c204
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "4984607"
---
# <a name="configure-benefits-management-parameters-per-company"></a>Konfigurowanie parametrów zarządzania świadczeniami w firmie

Dla każdej organizacji oferującej świadczenia należy skonfigurować ustawienia wiadomości e-mail z potwierdzeniem świadczeń.

## <a name="configure-confirmation-email-settings"></a>Konfigurowanie ustawień wiadomości e-mail z potwierdzeniem

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry Human Resources**.

2. Na karcie **Zarządzanie świadczeniami** wprowadź wartości w następujących polach: 

   | Pole | opis |
   | --- | --- |
   | **Wyślij wiadomość e-mail z potwierdzeniem** | Gdy ta funkcja jest włączona, do pracowników etatowych wysyłana jest wiadomość e-mail z potwierdzeniem, gdy zarejestrują się na świadczenia w obszarze Samoobsługa pracownika etatowego. |
   | **Szablon wiadomości e-mail z potwierdzeniem** | Wybierz szablon e-mail organizacji, który ma być stosowany podczas wysyłania potwierdzenia rejestracji. Jeśli nie wybierzesz szablonu, zostanie wysłana następująca ogólna wiadomość e-mail:<br><br>%EmployeeFirstName%,<br><br>Gratulacje! Twoja rejestracja na świadczenia została pomyślnie zakończona.<br><br>Dziękujemy,<br>Świadczenia w firmie <Company/Org name>. |
   | **Domyślny adres e-mail nadawcy** | Adres e-mail, który ma być użyty do wysłania wiadomości e-mail z potwierdzeniem. |

3. Wybierz opcję **Zapisz**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]