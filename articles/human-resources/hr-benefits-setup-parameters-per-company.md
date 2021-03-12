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
# <a name="configure-benefits-management-parameters-per-company"></a><span data-ttu-id="7ba2a-103">Konfigurowanie parametrów zarządzania świadczeniami w firmie</span><span class="sxs-lookup"><span data-stu-id="7ba2a-103">Configure Benefits management parameters per company</span></span>

<span data-ttu-id="7ba2a-104">Dla każdej organizacji oferującej świadczenia należy skonfigurować ustawienia wiadomości e-mail z potwierdzeniem świadczeń.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-104">For each organization that offers benefits, you must configure settings for benefits confirmation emails.</span></span>

## <a name="configure-confirmation-email-settings"></a><span data-ttu-id="7ba2a-105">Konfigurowanie ustawień wiadomości e-mail z potwierdzeniem</span><span class="sxs-lookup"><span data-stu-id="7ba2a-105">Configure confirmation email settings</span></span>

1. <span data-ttu-id="7ba2a-106">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-106">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="7ba2a-107">Na karcie **Zarządzanie świadczeniami** wprowadź wartości w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="7ba2a-107">In the **Benefits management** tab, specify values for the following fields:</span></span> 

   | <span data-ttu-id="7ba2a-108">Pole</span><span class="sxs-lookup"><span data-stu-id="7ba2a-108">Field</span></span> | <span data-ttu-id="7ba2a-109">opis</span><span class="sxs-lookup"><span data-stu-id="7ba2a-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="7ba2a-110">**Wyślij wiadomość e-mail z potwierdzeniem**</span><span class="sxs-lookup"><span data-stu-id="7ba2a-110">**Send confirmation email**</span></span> | <span data-ttu-id="7ba2a-111">Gdy ta funkcja jest włączona, do pracowników etatowych wysyłana jest wiadomość e-mail z potwierdzeniem, gdy zarejestrują się na świadczenia w obszarze Samoobsługa pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-111">When this feature is on, a confirmation email will be sent to employees when they check out from the benefits enrollment experience in Employee self-service.</span></span> |
   | <span data-ttu-id="7ba2a-112">**Szablon wiadomości e-mail z potwierdzeniem**</span><span class="sxs-lookup"><span data-stu-id="7ba2a-112">**Confirmation email template**</span></span> | <span data-ttu-id="7ba2a-113">Wybierz szablon e-mail organizacji, który ma być stosowany podczas wysyłania potwierdzenia rejestracji.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-113">Select the organization email template to use when sending the enrollment confirmation.</span></span> <span data-ttu-id="7ba2a-114">Jeśli nie wybierzesz szablonu, zostanie wysłana następująca ogólna wiadomość e-mail:</span><span class="sxs-lookup"><span data-stu-id="7ba2a-114">If you don't select a template, the following generic email will be sent:</span></span><br><br><span data-ttu-id="7ba2a-115">%EmployeeFirstName%,</span><span class="sxs-lookup"><span data-stu-id="7ba2a-115">%EmployeeFirstName%,</span></span><br><br><span data-ttu-id="7ba2a-116">Gratulacje!</span><span class="sxs-lookup"><span data-stu-id="7ba2a-116">Congratulations!</span></span> <span data-ttu-id="7ba2a-117">Twoja rejestracja na świadczenia została pomyślnie zakończona.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-117">You’ve successfully completed benefits enrollment.</span></span><br><br><span data-ttu-id="7ba2a-118">Dziękujemy,</span><span class="sxs-lookup"><span data-stu-id="7ba2a-118">Thank you,</span></span><br><span data-ttu-id="7ba2a-119">Świadczenia w firmie <Company/Org name>.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-119"><Company/Org name> Benefits.</span></span> |
   | <span data-ttu-id="7ba2a-120">**Domyślny adres e-mail nadawcy**</span><span class="sxs-lookup"><span data-stu-id="7ba2a-120">**Default email sender address**</span></span> | <span data-ttu-id="7ba2a-121">Adres e-mail, który ma być użyty do wysłania wiadomości e-mail z potwierdzeniem.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-121">The email address to use when sending the confirmation email.</span></span> |

3. <span data-ttu-id="7ba2a-122">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-122">Select **Save**.</span></span>