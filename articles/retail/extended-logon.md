---
title: "Konfigurowanie funkcjonalności logowania rozszerzonego w programach Cloud POS i MPOS"
description: Ten temat omawia opcje konfigurowania rozszerzonego logowania do aplikacji Cloud POS i Retail Modern POS (MPOS).
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 3e9ce03dfdc5dc027344186e0334b2ac2bc9341e
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-extended-logon-functionality-for-cloud-pos-and-mpos"></a><span data-ttu-id="edfaf-103">Konfigurowanie funkcjonalności logowania rozszerzonego w programach Cloud POS i MPOS</span><span class="sxs-lookup"><span data-stu-id="edfaf-103">Set up extended logon functionality for Cloud POS and MPOS</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="edfaf-104">Ten temat omawia opcje konfigurowania rozszerzonego logowania do aplikacji Cloud POS i Retail Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="edfaf-104">This topic covers your options for setting up extended logon for Cloud POS and Retail Modern POS (MPOS).</span></span>

<a name="setting-up-extended-logon"></a><span data-ttu-id="edfaf-105">Konfigurowanie logowania rozszerzonego</span><span class="sxs-lookup"><span data-stu-id="edfaf-105">Setting up extended logon</span></span>
=========================

<span data-ttu-id="edfaf-106">Konfiguracje masek kodów kreskowych można znaleźć w oknie **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Profile punktu sprzedaży** &gt; **Profile funkcji**.</span><span class="sxs-lookup"><span data-stu-id="edfaf-106">You can find the setup for bar code masks at **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS profiles** &gt; **Functionality profiles**.</span></span> <span data-ttu-id="edfaf-107">Na skróconej karcie **Funkcje** znajdują się następujące opcje, które są związane z logowaniem rozszerzonym.</span><span class="sxs-lookup"><span data-stu-id="edfaf-107">The **Functions** FastTab includes the following options that are related to extended logon.</span></span>

### <a name="staff-bar-code-logon"></a><span data-ttu-id="edfaf-108">Logowanie się pracowników za pomocą kodu kreskowego</span><span class="sxs-lookup"><span data-stu-id="edfaf-108">Staff bar code logon</span></span>

<span data-ttu-id="edfaf-109">Gdy wybrana jest opcja **Logowanie się pracowników za pomocą kodu kreskowego**, pracownicy, którzy do swoich poświadczeń w punkcie sprzedaży mają przypisane logowanie rozszerzone, mogą logować się za pomocą kodu kreskowego.</span><span class="sxs-lookup"><span data-stu-id="edfaf-109">When the **Staff bar code logon** option is enabled, workers who have an extended logon assigned to their point of sale (POS) credentials can log on by using a bar code.</span></span>

### <a name="staff-bar-code-logon-requires-password"></a><span data-ttu-id="edfaf-110">Logowanie się pracowników za pomocą kodu kreskowego wymaga hasła</span><span class="sxs-lookup"><span data-stu-id="edfaf-110">Staff bar code logon requires password</span></span>

<span data-ttu-id="edfaf-111">Jeśli włączona jest opcja **Logowanie się pracowników za pomocą kodu kreskowego wymaga hasła**, funkcja logowanie się pracowników za pomocą kodu kreskowego wybiera tylko tego pracownika, który jest przypisany do przedstawionego logowania rozszerzonego.</span><span class="sxs-lookup"><span data-stu-id="edfaf-111">When the **Staff bar code logon requires password** option is enabled, the staff bar code logon selects only the worker who is assigned to the extended logon that is presented.</span></span> <span data-ttu-id="edfaf-112">Pracownicy muszą nadal podać hasło, nawet gdy ta opcja jest wybrana.</span><span class="sxs-lookup"><span data-stu-id="edfaf-112">Workers must still enter their password when this option is enabled.</span></span>

### <a name="staff-card-logon"></a><span data-ttu-id="edfaf-113">Logowanie się pracowników za pomocą karty</span><span class="sxs-lookup"><span data-stu-id="edfaf-113">Staff card logon</span></span>

<span data-ttu-id="edfaf-114">Gdy wybrana jest opcja **Logowanie się pracowników za pomocą karty**, pracownicy, którzy do swoich poświadczeń w punkcie sprzedaży mają przypisane logowanie rozszerzone, mogą logować się za pomocą paska magnetycznego.</span><span class="sxs-lookup"><span data-stu-id="edfaf-114">When the **Staff card logon** option is enabled, workers who have an extended logon assigned to their POS credentials can log on by using a magnetic stripe.</span></span>

### <a name="staff-card-logon-requires-password"></a><span data-ttu-id="edfaf-115">Logowanie się pracowników za pomocą karty wymaga hasła</span><span class="sxs-lookup"><span data-stu-id="edfaf-115">Staff card logon requires password</span></span>

<span data-ttu-id="edfaf-116">Jeśli włączona jest opcja **Logowanie się pracowników za pomocą karty wymaga hasła**, logowanie się pracowników za pomocą karty wybiera tylko tego pracownika, który jest przypisany do przedstawionego logowania rozszerzonego.</span><span class="sxs-lookup"><span data-stu-id="edfaf-116">When the **Staff card logon requires password** option is enabled, the staff card logon selects only the worker who is assigned to the extended logon that is presented.</span></span> <span data-ttu-id="edfaf-117">Pracownicy muszą nadal podać hasło, nawet gdy ta opcja jest wybrana.</span><span class="sxs-lookup"><span data-stu-id="edfaf-117">Workers must still enter their password when this option is enabled.</span></span>

<a name="assigning-an-extended-logon"></a><span data-ttu-id="edfaf-118">Przypisywanie logowania rozszerzonego</span><span class="sxs-lookup"><span data-stu-id="edfaf-118">Assigning an extended logon</span></span>
===========================

<span data-ttu-id="edfaf-119">Domyślnie tylko menedżerowie mogą przypisywać pracownikom logowanie rozszerzone.</span><span class="sxs-lookup"><span data-stu-id="edfaf-119">By default, only managers can assign extended logon to workers.</span></span> <span data-ttu-id="edfaf-120">Aby przypisać logowanie rozszerzone, przejdź do opcji **Logowanie rozszerzone** w aplikacji punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="edfaf-120">To assign extended logon, go to **Extended log on** in POS.</span></span> <span data-ttu-id="edfaf-121">Następnie wyszukaj pracownika, wpisując w polu wyszukiwania jego identyfikator operatora.</span><span class="sxs-lookup"><span data-stu-id="edfaf-121">Then search for a worker by entering his or her operator ID in the search field.</span></span> <span data-ttu-id="edfaf-122">Wybierz pracownika, a następnie kliknij przycisk **Przypisz**.</span><span class="sxs-lookup"><span data-stu-id="edfaf-122">Select the worker, and then click **Assign**.</span></span> <span data-ttu-id="edfaf-123">Na następnej stronie przeciągnij lub zeskanuj kartę lub kod kreskowy do logowania rozszerzonego, aby przypisać pracownika.</span><span class="sxs-lookup"><span data-stu-id="edfaf-123">On the next page, swipe or scan the extended logon to assign to the worker.</span></span> <span data-ttu-id="edfaf-124">Jeśli odczyt danych się powiedzie, przycisk **OK** stanie się aktywny.</span><span class="sxs-lookup"><span data-stu-id="edfaf-124">If the swipe or scan is successfully read, the **OK** button becomes available.</span></span> <span data-ttu-id="edfaf-125">Kliknij **OK**, aby zapisać logowanie rozszerzone dla tego pracownika.</span><span class="sxs-lookup"><span data-stu-id="edfaf-125">Click **OK** to save the extended logon for that worker.</span></span>

<a name="deleting-an-extended-logon"></a><span data-ttu-id="edfaf-126">Anulowanie przypisania logowania rozszerzonego</span><span class="sxs-lookup"><span data-stu-id="edfaf-126">Deleting an extended logon</span></span>
==========================

<span data-ttu-id="edfaf-127">Aby anulować przypisanie logowania rozszerzonego do pracownika, znajdź pracownika za pomocą operacji **Logowanie rozszerzone**.</span><span class="sxs-lookup"><span data-stu-id="edfaf-127">To delete the extended logon that is assigned to a worker, search for the worker by using the **Extended log on** operation.</span></span> <span data-ttu-id="edfaf-128">Wybierz pracownika, a następnie kliknij przycisk **Anuluj przypisanie**.</span><span class="sxs-lookup"><span data-stu-id="edfaf-128">Select the worker, and then click **Unassign**.</span></span> <span data-ttu-id="edfaf-129">Wszystkie poświadczenia logowania rozszerzonego przypisane do tego pracownika są usuwane.</span><span class="sxs-lookup"><span data-stu-id="edfaf-129">All extended logon credentials that are associated with that worker are removed.</span></span>

<a name="extending-extended-logon"></a><span data-ttu-id="edfaf-130">Rozszerzanie logowania rozszerzonego</span><span class="sxs-lookup"><span data-stu-id="edfaf-130">Extending extended logon</span></span>
========================

<span data-ttu-id="edfaf-131">Usługę logowania można rozszerzyć o obsługę dodatkowych urządzeń do logowania rozszerzonego, takich jak skanery ręczne.</span><span class="sxs-lookup"><span data-stu-id="edfaf-131">The logon service can be extended to support additional extended logon devices, such as palm scanners.</span></span> <span data-ttu-id="edfaf-132">Aby uzyskać więcej informacji, zapoznaj się z dokumentacją rozszerzania punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="edfaf-132">For more information, see the POS extensibility documentation.</span></span>

<a name="using-extended-logon"></a><span data-ttu-id="edfaf-133">Używanie logowania rozszerzonego</span><span class="sxs-lookup"><span data-stu-id="edfaf-133">Using extended logon</span></span>
====================

<span data-ttu-id="edfaf-134">Jeśli logowanie rozszerzone jest skonfigurowane i pracownik ma przypisany kod kreskowy lub pasek magnetyczny, pracownik musi tylko przeciągnąć kartę magnetyczną w czytniku lub zeskanować kod kreskowy, gdy na ekranie wyświetlana jest strona logowania punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="edfaf-134">When extended logon is configured, and a worker has been assigned a bar code or magnetic stripe, the worker just has to swipe or scan his or her card while the POS logon page is displayed.</span></span> <span data-ttu-id="edfaf-135">Jeśli logowanie wymaga podania hasła, wyświetla się również monit o podanie hasła.</span><span class="sxs-lookup"><span data-stu-id="edfaf-135">If a password is also required before logon can proceed, the worker is prompted to enter his or her password.</span></span>




