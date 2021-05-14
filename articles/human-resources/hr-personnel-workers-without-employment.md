---
title: Pracownicy bez zatrudnienia
description: Pracownicy bez przyszłego, aktywnego lub historycznego zatrudnienia w organizacji są wyświetlani w formularzu Pracownicy bez zatrudnienia.
author: andreabichsel
ms.date: 04/06/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e1a137de25924f4c4ec6f6b1fe70f9d21af591c0
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924578"
---
# <a name="workers-without-employment"></a><span data-ttu-id="6f5de-103">Pracownicy bez zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="6f5de-103">Workers without employment</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="6f5de-104">Pracownicy bez przyszłego, aktywnego lub historycznego zatrudnienia w organizacji są wyświetlani w formularzu **Pracownicy bez zatrudnienia**.</span><span class="sxs-lookup"><span data-stu-id="6f5de-104">Workers with no future, active, or historical employment with your organization appear in the **Workers without employment** form.</span></span> <span data-ttu-id="6f5de-105">Pracownicy z tym stanem mogą pojawiać się podczas importowania pracowników bez rekordu zatrudnienia lub usuwania zatrudnienia pracownika za pośrednictwem opcji **Pracownicy > Historia zatrudnienia**.</span><span class="sxs-lookup"><span data-stu-id="6f5de-105">Workers with this status can appear when you import workers without an employment record, or when you delete a worker's employment via **Workers > Employment history**.</span></span>

<span data-ttu-id="6f5de-106">Domyślnie formularz **Pracownicy bez zatrudnienia** jest dostępny dla następujących ról:</span><span class="sxs-lookup"><span data-stu-id="6f5de-106">By default, the **Workers without employment** form is available to the following roles:</span></span>

- <span data-ttu-id="6f5de-107">Asystent ds. kadr</span><span class="sxs-lookup"><span data-stu-id="6f5de-107">Human Resources Assistant</span></span>
- <span data-ttu-id="6f5de-108">Menedżer ds. kadr</span><span class="sxs-lookup"><span data-stu-id="6f5de-108">Human Resources Manager</span></span>
- <span data-ttu-id="6f5de-109">Osoba rekrutująca</span><span class="sxs-lookup"><span data-stu-id="6f5de-109">Recruiter</span></span>
- <span data-ttu-id="6f5de-110">Menedżer wynagrodzeń i świadczeń</span><span class="sxs-lookup"><span data-stu-id="6f5de-110">Comp and Benefits Manager</span></span>
- <span data-ttu-id="6f5de-111">Administrator listy płac</span><span class="sxs-lookup"><span data-stu-id="6f5de-111">Payroll Administrator</span></span>
- <span data-ttu-id="6f5de-112">Menedżer ds. listy płac</span><span class="sxs-lookup"><span data-stu-id="6f5de-112">Payroll Manager</span></span>
- <span data-ttu-id="6f5de-113">Menedżer ds. szkoleń</span><span class="sxs-lookup"><span data-stu-id="6f5de-113">Training Manager</span></span>

<span data-ttu-id="6f5de-114">Z listy **Pracownicy bez zatrudnienia** można usunąć osoby.</span><span class="sxs-lookup"><span data-stu-id="6f5de-114">In the **Workers without employment** list, you can delete the individuals listed.</span></span> <span data-ttu-id="6f5de-115">Domyślnie to uprawnienie jest nadane roli Asystent ds. kadr.</span><span class="sxs-lookup"><span data-stu-id="6f5de-115">By default, this privilege is given to the Human Resources Assistant role.</span></span> <span data-ttu-id="6f5de-116">To uprawnienie można udzielić innym rolom, wykonując następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="6f5de-116">You can give this privilege to other roles with the following steps:</span></span>

1. <span data-ttu-id="6f5de-117">Wybierz opcję **Administrowanie systemem**, a następnie wybierz opcję **Konfiguracja zabezpieczeń**.</span><span class="sxs-lookup"><span data-stu-id="6f5de-117">Select **System administration**, and then select **Security configuration**.</span></span>

2. <span data-ttu-id="6f5de-118">Na karcie **uprawnienia** odfiltruj listę **uprawnień**, aby **obsługiwać pracowników**.</span><span class="sxs-lookup"><span data-stu-id="6f5de-118">In the **Privileges** tab, filter the **Privileges** list to **Maintain workers**.</span></span>

   <span data-ttu-id="6f5de-119">[![Filtrowanie listy uprawnień](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)</span><span class="sxs-lookup"><span data-stu-id="6f5de-119">[![Filter Privileges list](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)</span></span>

3. <span data-ttu-id="6f5de-120">W kolumnie **odwołania** wybierz **Wyświetl elementy menu**.</span><span class="sxs-lookup"><span data-stu-id="6f5de-120">In the **References** column, select **Display menu items**.</span></span>

4. <span data-ttu-id="6f5de-121">W kolumnie **Wyświetl elementy menu** wybierz **HcmWorkersWithoutEmployment**.</span><span class="sxs-lookup"><span data-stu-id="6f5de-121">In **Display menu items**, select **HcmWorkersWithoutEmployment**.</span></span>

   <span data-ttu-id="6f5de-122">[![Wybierz formularz](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)</span><span class="sxs-lookup"><span data-stu-id="6f5de-122">[![Select form](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)</span></span>

5. <span data-ttu-id="6f5de-123">Zmień ustawienie uprawnienia **Usuń** na **Udzielenie**.</span><span class="sxs-lookup"><span data-stu-id="6f5de-123">Set the **Delete** permission to **Grant**.</span></span>

6. <span data-ttu-id="6f5de-124">Wybierz kartę **nieopublikowane obiekty**.</span><span class="sxs-lookup"><span data-stu-id="6f5de-124">Select the **Unpublished objects** tab.</span></span>

7. <span data-ttu-id="6f5de-125">Wybierz opcję **Publikuj wszystko**.</span><span class="sxs-lookup"><span data-stu-id="6f5de-125">Select **Publish all**.</span></span>

   <span data-ttu-id="6f5de-126">[![Opublikuj zmiany](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)</span><span class="sxs-lookup"><span data-stu-id="6f5de-126">[![Publish changes](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]