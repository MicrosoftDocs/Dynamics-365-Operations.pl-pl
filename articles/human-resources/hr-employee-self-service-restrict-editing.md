---
title: Ogranicz edytowanie informacji osobistych
description: Ograniczanie pracownikom możliwości edytowania szczegółów kontaktu w Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c5e3eeb66d4f32b1fea1a43fff9f5b09d87d1f53
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018716"
---
# <a name="restrict-editing-of-personal-information"></a><span data-ttu-id="5cb0d-103">Ogranicz edytowanie informacji osobistych</span><span class="sxs-lookup"><span data-stu-id="5cb0d-103">Restrict editing of personal information</span></span>

[!include [applies to](../includes/applies-to-hr.md)]
[!include [preview feature](./includes/preview-feature.md)]

<span data-ttu-id="5cb0d-104">W tym temacie opisano sposób ograniczenia możliwości edytowania szczegółów kontaktów przez pracowników w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5cb0d-104">This topic describes how to restrict employees from editing contact details in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="5cb0d-105">Możesz chcieć uniemożliwić pracownikom edytowanie niektórych danych kontaktowych, takich jak lokalizacja firmy lub adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="5cb0d-105">You might want to prevent employees from editing certain contact details, such as their business location or email address.</span></span>

> [!NOTE]
> <span data-ttu-id="5cb0d-106">Aby można było korzystać z tej funkcji, należy najpierw włączyć funkcję **(Wersja zapoznawcza) Ogranicz pracownikom możliwość dodawania lub edytowania adresów i informacji kontaktowych w wybranych celach** w Zarządzaniu funkcjami.</span><span class="sxs-lookup"><span data-stu-id="5cb0d-106">To use this feature, you must first enable **(Preview) Restrict employees from adding or editing address and contact information for select purposes** in Feature management.</span></span> <span data-ttu-id="5cb0d-107">Aby uzyskać więcej informacji na temat włączania funkcji w wersji zapoznawczej, zobacz temat [Zarządzanie funkcjami](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="5cb0d-107">For more information about enabling preview features, see [Manage features](hr-admin-manage-features.md).</span></span><br><br><span data-ttu-id="5cb0d-108">![Włącz funkcje w wersji Preview](./media/hr-employee-self-service-restrict-enable.png)</span><span class="sxs-lookup"><span data-stu-id="5cb0d-108">![Enable preview feature](./media/hr-employee-self-service-restrict-enable.png)</span></span>

## <a name="choose-the-information-an-employee-can-add-or-edit"></a><span data-ttu-id="5cb0d-109">Wybierz informacje, które pracownik może dodać lub edytować</span><span class="sxs-lookup"><span data-stu-id="5cb0d-109">Choose the information an employee can add or edit</span></span>

1. <span data-ttu-id="5cb0d-110">W Human Resources wybierz opcję **Zarządzanie kadrami**, wybierz opcję **Łącza**, a następnie wybierz **Parametry Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="5cb0d-110">In Human Resources, select **Personnel management**, select **Links**, and then select **Human resources parameters**.</span></span>

   ![Przejdź do parametrów zasobów ludzkich](./media/hr-employee-self-service-human-resources-parameters.png)

2. <span data-ttu-id="5cb0d-112">Na stronie **Parametry zasobów ludzkich** wybierz kartę **Samoobsługa pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="5cb0d-112">On the **Human resources parameters** page, select the **Employee self service** tab.</span></span>

   ![Wybierz Samoobsługa pracownika etatowego](./media/hr-employee-self-service-tab.png)

3. <span data-ttu-id="5cb0d-114">Na karcie **Samoobsługa pracownika etatowego** usuń zaznaczenie wszystkich informacji w sekcji **Adres i informacje kontaktowe**, których nie chcesz, aby pracownicy mogli dodawać ani edytować.</span><span class="sxs-lookup"><span data-stu-id="5cb0d-114">On the **Employee self service** tab, uncheck all information in the **Address and contact information** section that you don't want employees to add or edit.</span></span> <span data-ttu-id="5cb0d-115">W tym przykładzie odznaczyliśmy informacje o kontakcie **Biznesowym**.</span><span class="sxs-lookup"><span data-stu-id="5cb0d-115">In this example, we've unchecked **Business** contact information.</span></span>

   ![Ogranicz edytowanie informacji o kontakcie biznesowym](./media/hr-employee-self-service-restrict-business.png)

4. <span data-ttu-id="5cb0d-117">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="5cb0d-117">Select **Save**.</span></span>

   ![Zapisz zmiany](./media/hr-employee-self-service-restrict-save.png)

## <a name="employee-experience"></a><span data-ttu-id="5cb0d-119">Doświadczenie pracownika</span><span class="sxs-lookup"><span data-stu-id="5cb0d-119">Employee experience</span></span>

<span data-ttu-id="5cb0d-120">Gdy ograniczysz pracownikom możliwość dodawania lub edytowania danych kontaktowych, będą mogli wyświetlać te informacje, ale nie mogą ich zmienić.</span><span class="sxs-lookup"><span data-stu-id="5cb0d-120">After you've restricted employees from adding or editing contact details, they can see the information, but can't change it.</span></span>

<span data-ttu-id="5cb0d-121">W tym przykładzie pracownicy, kiedy pracownicy nie mogą edytować szczegółów kontaktów **biznesowych**, nadal mogą zobaczyć te informacje w formularzu Samoobsługa pracownika:</span><span class="sxs-lookup"><span data-stu-id="5cb0d-121">In this example, where employees are restricted from editing **Business** contact details, they can still see the information in Employee self service:</span></span>

![Wyświetl szczegóły kontaktu biznesowego](./media/hr-employee-self-service-restrict-view.png)

<span data-ttu-id="5cb0d-123">Jednak po wybraniu szczegółów kontaktu biznesowego okienko **Edycja adresu** jest wyświetlane jako tylko do odczytu i nie można zmienić żadnego z pól.</span><span class="sxs-lookup"><span data-stu-id="5cb0d-123">However, when they select the business contact details, the **Edit address** pane appears as read-only, and they can't change any of the fields.</span></span>

![Szczegóły kontaktu biznesowego są wyświetlane jako tylko do odczytu](./media/hr-employee-self-service-restrict-read-only.png)

<span data-ttu-id="5cb0d-125">Ponadto, jeśli wybiorą opcję **Dodaj**, aby dodać nowy adres, nie będą mogli wybrać opcji **Firma** z listy rozwijanej **Cel**.</span><span class="sxs-lookup"><span data-stu-id="5cb0d-125">In addition, if they select **Add** to add a new address, they can't select **Business** from the **Purpose** dropdown box.</span></span>

![Pracownik nie może dodać adresu firmy](./media/hr-employee-self-service-restrict-add.png)

<span data-ttu-id="5cb0d-127">Pracownicy mają takie same wrażenia, gdy wybierają **Dane kontaktowe** na stronie **Informacje osobiste** i dodają nowy adres.</span><span class="sxs-lookup"><span data-stu-id="5cb0d-127">Employees get the same experience when they select **Contact details** on the **Personal information** page and add a new address.</span></span> <span data-ttu-id="5cb0d-128">Na liście rozwijanej **Cel** są wyświetlane tylko typy informacji, które mogą dodawać.</span><span class="sxs-lookup"><span data-stu-id="5cb0d-128">The **Purpose** dropdown box only displays the types of information they can add.</span></span> 

![Pracownik nie może wybrać firmy z listy rozwijanej Cel](./media/hr-employee-self-service-restrict-purpose.png)

<span data-ttu-id="5cb0d-130">**Szczegóły osoby kontaktowej** będą teraz wyświetlać **Cel** w siatce.</span><span class="sxs-lookup"><span data-stu-id="5cb0d-130">**Contact details** now shows **Purpose** in the grid.</span></span>

![Cel jest wyświetlany w siatce szczegółów kontaktu](./media/hr-employee-self-service-restrict-purpose-grid.png)

## <a name="see-also"></a><span data-ttu-id="5cb0d-132">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="5cb0d-132">See also</span></span>

[<span data-ttu-id="5cb0d-133">Omówienie samoobsługi dla pracownika etatowego i menedżera</span><span class="sxs-lookup"><span data-stu-id="5cb0d-133">Employee and Manager self service overview</span></span>](hr-employee-manager-self-service-overview.md)<br>
[<span data-ttu-id="5cb0d-134">Konfigurowanie parametrów rozwiązania Human Resources</span><span class="sxs-lookup"><span data-stu-id="5cb0d-134">Configure Human resources parameters</span></span>](hr-setup-parameters.md)<br>
[<span data-ttu-id="5cb0d-135">Edytowanie informacji osobistych</span><span class="sxs-lookup"><span data-stu-id="5cb0d-135">Edit personal information</span></span>](hr-employee-manager-self-service-edit-personal-information.md)