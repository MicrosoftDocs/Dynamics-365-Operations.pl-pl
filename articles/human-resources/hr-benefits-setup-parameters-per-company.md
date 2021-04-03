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
ms.openlocfilehash: 31f30c3d268132327074e931b714b5b2ee3ec5ac
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466647"
---
# <a name="configure-benefits-management-parameters-per-company"></a><span data-ttu-id="68e56-103">Konfigurowanie parametrów zarządzania świadczeniami w firmie</span><span class="sxs-lookup"><span data-stu-id="68e56-103">Configure Benefits management parameters per company</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="68e56-104">Dla każdej organizacji oferującej świadczenia należy skonfigurować ustawienia wiadomości e-mail z potwierdzeniem świadczeń.</span><span class="sxs-lookup"><span data-stu-id="68e56-104">For each organization that offers benefits, you must configure settings for benefits confirmation emails.</span></span>

## <a name="configure-confirmation-email-settings"></a><span data-ttu-id="68e56-105">Konfigurowanie ustawień wiadomości e-mail z potwierdzeniem</span><span class="sxs-lookup"><span data-stu-id="68e56-105">Configure confirmation email settings</span></span>

1. <span data-ttu-id="68e56-106">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="68e56-106">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="68e56-107">Na karcie **Zarządzanie świadczeniami** wprowadź wartości w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="68e56-107">In the **Benefits management** tab, specify values for the following fields:</span></span> 

   | <span data-ttu-id="68e56-108">Pole</span><span class="sxs-lookup"><span data-stu-id="68e56-108">Field</span></span> | <span data-ttu-id="68e56-109">opis</span><span class="sxs-lookup"><span data-stu-id="68e56-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="68e56-110">**Wyślij wiadomość e-mail z potwierdzeniem**</span><span class="sxs-lookup"><span data-stu-id="68e56-110">**Send confirmation email**</span></span> | <span data-ttu-id="68e56-111">Gdy ta funkcja jest włączona, do pracowników etatowych wysyłana jest wiadomość e-mail z potwierdzeniem, gdy zarejestrują się na świadczenia w obszarze Samoobsługa pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="68e56-111">When this feature is on, a confirmation email will be sent to employees when they check out from the benefits enrollment experience in Employee self-service.</span></span> |
   | <span data-ttu-id="68e56-112">**Szablon wiadomości e-mail z potwierdzeniem**</span><span class="sxs-lookup"><span data-stu-id="68e56-112">**Confirmation email template**</span></span> | <span data-ttu-id="68e56-113">Wybierz szablon e-mail organizacji, który ma być stosowany podczas wysyłania potwierdzenia rejestracji.</span><span class="sxs-lookup"><span data-stu-id="68e56-113">Select the organization email template to use when sending the enrollment confirmation.</span></span> <span data-ttu-id="68e56-114">Jeśli nie wybierzesz szablonu, zostanie wysłana następująca ogólna wiadomość e-mail:</span><span class="sxs-lookup"><span data-stu-id="68e56-114">If you don't select a template, the following generic email will be sent:</span></span><br><br><span data-ttu-id="68e56-115">%EmployeeFirstName%.</span><span class="sxs-lookup"><span data-stu-id="68e56-115">%EmployeeFirstName%,</span></span><br><br><span data-ttu-id="68e56-116">Gratulacje!</span><span class="sxs-lookup"><span data-stu-id="68e56-116">Congratulations!</span></span> <span data-ttu-id="68e56-117">Twoja rejestracja na świadczenia została pomyślnie zakończona.</span><span class="sxs-lookup"><span data-stu-id="68e56-117">You’ve successfully completed benefits enrollment.</span></span><br><br><span data-ttu-id="68e56-118">Dziękujemy,</span><span class="sxs-lookup"><span data-stu-id="68e56-118">Thank you,</span></span><br><span data-ttu-id="68e56-119">Świadczenia w firmie <Company/Org name>.</span><span class="sxs-lookup"><span data-stu-id="68e56-119"><Company/Org name> Benefits.</span></span> |
   | <span data-ttu-id="68e56-120">**Domyślny adres e-mail nadawcy**</span><span class="sxs-lookup"><span data-stu-id="68e56-120">**Default email sender address**</span></span> | <span data-ttu-id="68e56-121">Adres e-mail, który ma być użyty do wysłania wiadomości e-mail z potwierdzeniem.</span><span class="sxs-lookup"><span data-stu-id="68e56-121">The email address to use when sending the confirmation email.</span></span> |

3. <span data-ttu-id="68e56-122">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="68e56-122">Select **Save**.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]