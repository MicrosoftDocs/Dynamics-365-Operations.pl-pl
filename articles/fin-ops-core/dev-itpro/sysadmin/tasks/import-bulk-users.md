---
title: Importowanie użytkowników z usługi Azure Active Directory
description: Ta procedura umożliwia administratorom systemów ręczne importowanie wybranych użytkowników lub importowanie dużej liczby użytkowników z usługi Azure Active Directory.
author: peakerbl
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e9f03ae7197790c1aac6ebf3cb94ff7963b1291e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745796"
---
# <a name="import-users-from-azure-active-directory"></a><span data-ttu-id="367ac-103">Importowanie użytkowników z usługi Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="367ac-103">Import users from Azure Active Directory</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a><span data-ttu-id="367ac-104">Importowanie wybranych użytkowników</span><span class="sxs-lookup"><span data-stu-id="367ac-104">Import select users</span></span>

<span data-ttu-id="367ac-105">Ta procedura umożliwia administratorom systemów importowanie wybranych użytkowników z usługi Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="367ac-105">This procedure can be used by system administrators to import select users from Azure Active Directory (Azure AD).</span></span>

1. <span data-ttu-id="367ac-106">Użytkownicy zostaną zaimportowani z firmą w bieżącej sesji jako ich firmą domyślną.</span><span class="sxs-lookup"><span data-stu-id="367ac-106">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="367ac-107">W razie potrzeby przed importowaniem użytkowników zmień bieżącą firmę.</span><span class="sxs-lookup"><span data-stu-id="367ac-107">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="367ac-108">Wybierz **Administrowanie systemem > Użytkownicy > Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="367ac-108">Go to **System administration > Users > User** s.</span></span>
3. <span data-ttu-id="367ac-109">Kliknij opcję **Importuj użytkowników**.</span><span class="sxs-lookup"><span data-stu-id="367ac-109">Click **Import users**.</span></span>
4. <span data-ttu-id="367ac-110">Zaznacz użytkowników, którzy mają zostać zaimportowani, i wybierz opcję **Importuj użytkowników**.</span><span class="sxs-lookup"><span data-stu-id="367ac-110">Select the users that should be imported and select **Import users**.</span></span>

<span data-ttu-id="367ac-111">Po zakończeniu importu trzeba będzie przypisać role użytkownikom.</span><span class="sxs-lookup"><span data-stu-id="367ac-111">After import is completed it will be required to assign roles to users.</span></span>

## <a name="import-users-in-bulk"></a><span data-ttu-id="367ac-112">Zbiorowe importowanie użytkowników</span><span class="sxs-lookup"><span data-stu-id="367ac-112">Import users in bulk</span></span>

<span data-ttu-id="367ac-113">Ta procedura umożliwia administratorom systemów importowanie dużej liczby użytkowników z usługi Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="367ac-113">This procedure can be used by system administrators to import a large number of users from Azure Active Directory.</span></span>
<span data-ttu-id="367ac-114">Zauważ, że w przypadku korzystania z opcji importu wsadowego nie można wybierać użytkowników.</span><span class="sxs-lookup"><span data-stu-id="367ac-114">Note that it is not possible to select users when using the Batch import option.</span></span>

## <a name="run-the-import-as-a-batch-job"></a><span data-ttu-id="367ac-115">Wykonywanie importu jako zadania wsadowego</span><span class="sxs-lookup"><span data-stu-id="367ac-115">Run the import as a batch job</span></span>
1. <span data-ttu-id="367ac-116">Użytkownicy zostaną zaimportowani z firmą w bieżącej sesji jako ich firmą domyślną.</span><span class="sxs-lookup"><span data-stu-id="367ac-116">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="367ac-117">W razie potrzeby przed importowaniem użytkowników zmień bieżącą firmę.</span><span class="sxs-lookup"><span data-stu-id="367ac-117">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="367ac-118">Wybierz **Administrowanie systemem > Użytkownicy > Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="367ac-118">Go to **System administration > Users > Users**.</span></span>
3. <span data-ttu-id="367ac-119">Kliknij opcję **Import wsadowy**.</span><span class="sxs-lookup"><span data-stu-id="367ac-119">Click **Batch import**.</span></span>
4. <span data-ttu-id="367ac-120">Rozwiń sekcję **Uruchom w tle**.</span><span class="sxs-lookup"><span data-stu-id="367ac-120">Expand the **Run in the background** section.</span></span>
4. <span data-ttu-id="367ac-121">W polu **Przetwarzanie wsadowe** zaznacz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="367ac-121">Select **Yes** in the **Batch processing** field.</span></span>
6. <span data-ttu-id="367ac-122">W polu **Grupa zadań wsadowych** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="367ac-122">In the **Batch group** field, enter or select a value.</span></span> <span data-ttu-id="367ac-123">Ten krok jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="367ac-123">This is an optional step.</span></span>  
7. <span data-ttu-id="367ac-124">W polu **Prywatne** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="367ac-124">Select **Yes** in the **Private** field.</span></span> <span data-ttu-id="367ac-125">Ten krok jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="367ac-125">This is an optional step.</span></span>  
8. <span data-ttu-id="367ac-126">W polu **Zadanie o znaczeniu krytycznym** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="367ac-126">Select **Yes** in the **Critical job** field.</span></span> <span data-ttu-id="367ac-127">Ten krok jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="367ac-127">This is an optional step.</span></span>  
9. <span data-ttu-id="367ac-128">W polu **Monitorowanie kategorii** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="367ac-128">In the **Monitoring category** field, select an option.</span></span>
10. <span data-ttu-id="367ac-129">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="367ac-129">Click **OK**.</span></span>

<span data-ttu-id="367ac-130">Po zakończeniu importu trzeba będzie przypisać role użytkownikom.</span><span class="sxs-lookup"><span data-stu-id="367ac-130">After import is completed, it will be required to assign roles to users.</span></span>

## <a name="run-in-a-sandbox-environment"></a><span data-ttu-id="367ac-131">Uruchamianie w środowisku piaskownicy</span><span class="sxs-lookup"><span data-stu-id="367ac-131">Run in a sandbox environment</span></span>
1. <span data-ttu-id="367ac-132">Wybierz opcję **Import wsadowy**.</span><span class="sxs-lookup"><span data-stu-id="367ac-132">Select **Batch import**.</span></span>
2. <span data-ttu-id="367ac-133">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="367ac-133">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]