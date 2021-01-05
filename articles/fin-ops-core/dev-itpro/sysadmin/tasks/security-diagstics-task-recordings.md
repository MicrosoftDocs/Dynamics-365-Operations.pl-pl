---
title: Diagnostyka zabezpieczeń dla nagrań zadań
description: Ten temat zawiera informacje o sposobach analizowania wymagań dotyczących uprawnień zabezpieczeń i zarządzania nimi na podstawie nagrania zadania.
author: Peakerbl
manager: AnnBe
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 10.0.9
ms.openlocfilehash: 88eb90b35f1a9754cc4daa01d8f40cdf712db4f8
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679797"
---
# <a name="security-diagnostics-for-task-recordings"></a><span data-ttu-id="b32c0-103">Diagnostyka zabezpieczeń dla nagrań zadań</span><span class="sxs-lookup"><span data-stu-id="b32c0-103">Security diagnostics for task recordings</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a><span data-ttu-id="b32c0-104">Przed rozpoczęciem</span><span class="sxs-lookup"><span data-stu-id="b32c0-104">Before you begin</span></span>

<span data-ttu-id="b32c0-105">Ten temat zawiera informacje o sposobach analizowania wymagań dotyczących uprawnień zabezpieczeń i zarządzania nimi na podstawie nagrania zadania.</span><span class="sxs-lookup"><span data-stu-id="b32c0-105">This topic provides information about how to analyze and manage security permission requirements based on a task recording.</span></span> <span data-ttu-id="b32c0-106">Przed wykonaniem kroków opisanych w tym temacie należy utworzyć nagranie zadania procesu biznesowego do przeanalizowania.</span><span class="sxs-lookup"><span data-stu-id="b32c0-106">Before you complete the steps in this topic, you must have a task recording of the business process that you want to analyze.</span></span> <span data-ttu-id="b32c0-107">Aby zarejestrować proces biznesowy, zapoznać się z tematem [Zasoby rejestratora zadań](../../user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="b32c0-107">To record a business process, see [Task recorder resources](../../user-interface/task-recorder.md).</span></span> 

## <a name="manage-security-for-a-task-recording"></a><span data-ttu-id="b32c0-108">Zarządzanie zabezpieczeniami na potrzeby nagrania zadania</span><span class="sxs-lookup"><span data-stu-id="b32c0-108">Manage security for a task recording</span></span>

1. <span data-ttu-id="b32c0-109">Przejdź do pozycji **Administrowanie systemem** > **Zabezpieczenia** > **Diagnostyka zabezpieczeń na potrzeby nagrania zadania**.</span><span class="sxs-lookup"><span data-stu-id="b32c0-109">Go to **System administration** > **Security** > **Security diagnostic for task recording**.</span></span>
2. <span data-ttu-id="b32c0-110">Otwórz nagranie zadania z jego lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="b32c0-110">Open the task recording from its location.</span></span> <span data-ttu-id="b32c0-111">Wybierz opcję **Otwórz z tego komputera** lub **Otwórz z usług Lifecycle Services**, a następnie wybierz pozycję **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="b32c0-111">Select **Open from this PC** or **Open from Lifecycle Services**, and then select **Close**.</span></span>
3. <span data-ttu-id="b32c0-112">Spowoduje to otwarcie strony **Szczegóły elementu menu zabezpieczeń**, na której znajdują się obiekty zabezpieczeń wymagane w procesie.</span><span class="sxs-lookup"><span data-stu-id="b32c0-112">This will open the **Security menu item details** page that lists the security objects required for the process.</span></span>

 > [!NOTE]
 > <span data-ttu-id="b32c0-113">Elementów **Akcja** i **Dane wyjściowe** nie ma na liście.</span><span class="sxs-lookup"><span data-stu-id="b32c0-113">The **Action** and **Output** menu items are not included in the list.</span></span>

4. <span data-ttu-id="b32c0-114">W polu **Identyfikator użytkownika** wybierz użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b32c0-114">In the **User ID** field, select a user.</span></span> <span data-ttu-id="b32c0-115">Jeśli użytkownik nie ma uprawnień do niektórych elementów menu, pole **Brakujące uprawnienia** zostanie zaktualizowane do wartości **Tak**.</span><span class="sxs-lookup"><span data-stu-id="b32c0-115">If the user does not have permissions for some menu items, the **Missing permissions** field will update to **Yes**.</span></span>
  
  ![Strona szczegółów elementu menu zabezpieczeń](../media/Security-Menu-Item-Details.png)

5. <span data-ttu-id="b32c0-117">Wybierz pozycję **Dodaj odwołanie**, aby wyświetlić listę obiektów zabezpieczeń, w tym role, obowiązki i uprawnienia, które przyznają brakujące uprawnienie.</span><span class="sxs-lookup"><span data-stu-id="b32c0-117">Select **Add Reference** to see a list of the security objects, including roles, duties, and privileges that grant the missing permission.</span></span>
6. <span data-ttu-id="b32c0-118">Wybierz obiekt zabezpieczeń z listy:</span><span class="sxs-lookup"><span data-stu-id="b32c0-118">Select a security object from the list:</span></span>

    - <span data-ttu-id="b32c0-119">Jeśli wybrano pozycję **Rola**, wybierz opcję **Dodaj rolę do użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="b32c0-119">If **Role** is selected, select **Add role to user**.</span></span> <span data-ttu-id="b32c0-120">Spowoduje to otwarcie strony **Przypisywanie użytkowników do ról**.</span><span class="sxs-lookup"><span data-stu-id="b32c0-120">This will open the **Assign users to roles** page.</span></span> <span data-ttu-id="b32c0-121">Więcej informacji można znaleźć na stronie [Przypisywanie użytkowników do ról zabezpieczeń](assign-users-security-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b32c0-121">For more information, see [Assign users to security roles](assign-users-security-roles.md) page.</span></span>
    - <span data-ttu-id="b32c0-122">Jeśli wybrano pozycję **Obowiązek**, wybierz opcję **Dodaj obowiązek do roli**, wybierz role, do których ma zostać dodany obowiązek, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b32c0-122">If **Duty** is selected, select **Add duty to role**, select the roles that the duty should be added to, and then select **OK**.</span></span>
    - <span data-ttu-id="b32c0-123">Jeśli wybrano pozycję **Uprawnienie**, wybierz opcję **Dodaj uprawnienie do obowiązków**, wybierz role, do których ma zostać dodany obowiązek, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b32c0-123">If **Privilege** is selected, select **Add privilege to duties**, select the roles that the duty should be added to, and then select **OK**.</span></span>
