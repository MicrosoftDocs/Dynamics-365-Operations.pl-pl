---
title: Konfigurowanie kategorii konta głównego
description: W tym temacie wyjaśniono sposób konfigurowania kategorii konta głównego w Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 957fdc184410dc85f54cd3163799a9003f0727bb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222226"
---
# <a name="set-up-main-account-categories"></a><span data-ttu-id="53c56-103">Konfigurowanie kategorii konta głównego</span><span class="sxs-lookup"><span data-stu-id="53c56-103">Set up main account categories</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="53c56-104">W tym temacie wyjaśniono sposób konfigurowania kategorii konta głównego.</span><span class="sxs-lookup"><span data-stu-id="53c56-104">This topic explains how to set up main account categories.</span></span> <span data-ttu-id="53c56-105">Kategorie kont głównych są używane dla domyślnych raportów w sprawozdawczości finansowej i programie Power BI.</span><span class="sxs-lookup"><span data-stu-id="53c56-105">Main account categories are used for the default reports in financial reporting and in Power BI.</span></span> <span data-ttu-id="53c56-106">Kategoriom kont głównych, które są tworzone domyślnie, można zmienić nazwy, ale nie można ich usunąć.</span><span class="sxs-lookup"><span data-stu-id="53c56-106">Main account categories that are created by default can be renamed but not deleted.</span></span> <span data-ttu-id="53c56-107">Można tworzyć dodatkowe kategorie kont i używać ich na potrzeby raportowania i analizy.</span><span class="sxs-lookup"><span data-stu-id="53c56-107">Additional account categories can be created and used for reporting and analysis purposes.</span></span> <span data-ttu-id="53c56-108">Ten temat wykorzystuje firmę demonstracyjną „USMF”.</span><span class="sxs-lookup"><span data-stu-id="53c56-108">This topic uses the USMF demo company.</span></span>

## <a name="create-a-main-account-category"></a><span data-ttu-id="53c56-109">Tworzenie kategorii konta głównego</span><span class="sxs-lookup"><span data-stu-id="53c56-109">Create a main account category</span></span>
1. <span data-ttu-id="53c56-110">W okienku nawigacji wybierz kolejno **Moduły > Księga główna > Plan kont > Konta > Kategorie kont głównych**.</span><span class="sxs-lookup"><span data-stu-id="53c56-110">In the navigation pane, go to **Modules > General Ledger > Chart of accounts > Accounts > Main account categories**.</span></span>
2. <span data-ttu-id="53c56-111">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="53c56-111">Select **New**.</span></span>
3. <span data-ttu-id="53c56-112">W polu **Kategoria konta głównego** wprowadź unikatową nazwę.</span><span class="sxs-lookup"><span data-stu-id="53c56-112">In the **Main account category** field, enter a unique name.</span></span>
4. <span data-ttu-id="53c56-113">W **polu Opis** wprowadź opis kategorii kont głównych.</span><span class="sxs-lookup"><span data-stu-id="53c56-113">In the **Description field**, enter a description for the main account category.</span></span>
5. <span data-ttu-id="53c56-114">W polu **Typ konta głównego** zaznacz typ konta głównego, który zostanie powiązany z kategorią.</span><span class="sxs-lookup"><span data-stu-id="53c56-114">In the **Main account type** field, select the main account type that will be linked to the category.</span></span>

## <a name="link-main-accounts-to-account-category"></a><span data-ttu-id="53c56-115">Łączenie kont głównych z kategorią konta</span><span class="sxs-lookup"><span data-stu-id="53c56-115">Link main accounts to account category</span></span>
1. <span data-ttu-id="53c56-116">Kliknij opcję **Połącz konta główne**.</span><span class="sxs-lookup"><span data-stu-id="53c56-116">Click **Link main accounts**.</span></span>
2. <span data-ttu-id="53c56-117">Z listy wybierz konta główne, które mają zostać przypisane do kategorii konta głównego, zaznaczając odpowiednie pola w **Połączonej** kolumnie.</span><span class="sxs-lookup"><span data-stu-id="53c56-117">In the list, select the main accounts to assign to the main account category by checking the boxes in the **Linked** column.</span></span> <span data-ttu-id="53c56-118">Przypisanie kont głównych do kategorii konta głównego spowoduje agregację sald kont, gdy ta kategoria jest używana do sprawozdawczości finansowej i analizy.</span><span class="sxs-lookup"><span data-stu-id="53c56-118">Assigning main accounts to a main account category will aggregate the balances of the accounts when that category is used for financial reporting and analysis.</span></span>  
3. <span data-ttu-id="53c56-119">Zaznacz lub wyczyść pole wyboru **Połączone**, aby wybrać konta główne.</span><span class="sxs-lookup"><span data-stu-id="53c56-119">Select or clear the **Linked** option to choose the main accounts.</span></span>
4. <span data-ttu-id="53c56-120">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="53c56-120">Select **OK**.</span></span>
5. <span data-ttu-id="53c56-121">Wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="53c56-121">Select **Yes**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]