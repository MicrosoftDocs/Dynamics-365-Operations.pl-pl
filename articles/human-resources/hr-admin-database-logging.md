---
title: Konfigurowanie i zarządzanie rejestrowaniem bazy danych
description: Można śledzić zmiany w tabelach i polach w Dynamics 365 Human Resources z rejestrowaniem w bazie danych.
author: andreabichsel
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 50346cc495fe08f49137dba59dbcbb3f7f838c7b
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2021
ms.locfileid: "5129286"
---
# <a name="configure-and-manage-database-logging"></a><span data-ttu-id="4f261-103">Konfigurowanie i zarządzanie rejestrowaniem bazy danych</span><span class="sxs-lookup"><span data-stu-id="4f261-103">Configure and manage database logging</span></span>

<span data-ttu-id="4f261-104">Można śledzić zmiany w tabelach i polach w Dynamics 365 Human Resources z rejestrowaniem w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="4f261-104">You can track changes to tables and fields in Dynamics 365 Human Resources with database logging.</span></span> <span data-ttu-id="4f261-105">W tym temacie opisano sposób:</span><span class="sxs-lookup"><span data-stu-id="4f261-105">This topic describes how to:</span></span>

- <span data-ttu-id="4f261-106">Zarządzanie zabezpieczeniami i wydajnością dla rejestrowania w bazie danych</span><span class="sxs-lookup"><span data-stu-id="4f261-106">Manage security and performance for database logging</span></span>
- <span data-ttu-id="4f261-107">Konfigurowanie rejestrowania bazy danych</span><span class="sxs-lookup"><span data-stu-id="4f261-107">Set up database logging</span></span>
- <span data-ttu-id="4f261-108">Oczyszczanie dzienników bazy danych</span><span class="sxs-lookup"><span data-stu-id="4f261-108">Clean up database logs</span></span>

## <a name="overview-of-database-logging"></a><span data-ttu-id="4f261-109">Omówienie rejestrowania w bazie danych</span><span class="sxs-lookup"><span data-stu-id="4f261-109">Overview of database logging</span></span>

<span data-ttu-id="4f261-110">Można śledzić zmiany rejestrowania w bazie danych w tabelach i polach w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4f261-110">Database logging tracks specific changes to Microsoft Dynamics 365 Human Resources tables and fields.</span></span> <span data-ttu-id="4f261-111">Te zmiany obejmują wstawianie, aktualizowanie lub usuwanie.</span><span class="sxs-lookup"><span data-stu-id="4f261-111">These changes include inserting, updating, or deleting.</span></span> <span data-ttu-id="4f261-112">Rejestrowanie w bazie danych zapisuje rekord zmian w tabelach lub polach w tabeli dziennika bazy danych.</span><span class="sxs-lookup"><span data-stu-id="4f261-112">Database logging stores a record of changes to tables or fields in the database log table.</span></span>

<span data-ttu-id="4f261-113">Do zastosowań biznesowych w rejestrowaniu bazy danych należą:</span><span class="sxs-lookup"><span data-stu-id="4f261-113">The business uses of database logging include:</span></span>

- <span data-ttu-id="4f261-114">Tworzenie rekordu inspekcji zmian w konkretnych tabelach zawierających poufne informacje.</span><span class="sxs-lookup"><span data-stu-id="4f261-114">Creating an audit record of changes to specific tables that contain sensitive information.</span></span>
- <span data-ttu-id="4f261-115">Śledzenie pojedynczych transakcji.</span><span class="sxs-lookup"><span data-stu-id="4f261-115">Tracking single transactions.</span></span> <span data-ttu-id="4f261-116">Rejestrowanie w bazie danych nie jest przeznaczone do śledzenia zautomatyzowanych transakcji uruchamianych w zadaniach wsadowych.</span><span class="sxs-lookup"><span data-stu-id="4f261-116">Database logging isn't intended for tracking automated transactions that run in batch jobs.</span></span>

## <a name="security-for-database-logging"></a><span data-ttu-id="4f261-117">Zabezpieczenia dotyczące rejestrowania w bazie danych</span><span class="sxs-lookup"><span data-stu-id="4f261-117">Security for database logging</span></span>

<span data-ttu-id="4f261-118">Dzienniki bazy danych mogą zawierać dane poufne.</span><span class="sxs-lookup"><span data-stu-id="4f261-118">Database logs can contain sensitive data.</span></span> <span data-ttu-id="4f261-119">Umożliwia ograniczenie dostępu, aby obejmował tylko role zabezpieczeń wymagające dostępu do danych dziennika.</span><span class="sxs-lookup"><span data-stu-id="4f261-119">Limit access to include only security roles that need access to the log data.</span></span>

## <a name="database-logging-and-performance"></a><span data-ttu-id="4f261-120">Rejestrowanie i wydajność bazy danych</span><span class="sxs-lookup"><span data-stu-id="4f261-120">Database logging and performance</span></span>

<span data-ttu-id="4f261-121">Podczas gdy wartość jest cenna od perspektywy biznesowej, rejestrowanie w bazie danych może być kosztowne w użyciu i zarządzaniu zasobami.</span><span class="sxs-lookup"><span data-stu-id="4f261-121">While valuable from a business perspective, database logging can be expensive in resource use and management.</span></span> <span data-ttu-id="4f261-122">Wpływ rejestrowania bazy danych na wydajność obejmuje:</span><span class="sxs-lookup"><span data-stu-id="4f261-122">The performance implications of database logging include:</span></span>

- <span data-ttu-id="4f261-123">Tabela dziennika bazy danych może szybko rosnąć i powodować zwiększenie rozmiaru bazy danych.</span><span class="sxs-lookup"><span data-stu-id="4f261-123">The database log table can grow quickly and cause an increase in the size of the database.</span></span> <span data-ttu-id="4f261-124">Wzrost zależy od ilości zarejestrowanych danych, które mają zostać zachowane.</span><span class="sxs-lookup"><span data-stu-id="4f261-124">Growth depends on the amount of logged data that you decide to keep.</span></span> <span data-ttu-id="4f261-125">Domyślnie tabela dziennika bazy danych obsługuje tylko 30 dni danych dziennika.</span><span class="sxs-lookup"><span data-stu-id="4f261-125">By default, the database log table maintains only 30 days of log data.</span></span> 

- <span data-ttu-id="4f261-126">Rejestrowanie bazy danych może niekorzystnie wpłynąć na długotrwałe procesy, takie jak długotrwałe importowanie danych.</span><span class="sxs-lookup"><span data-stu-id="4f261-126">Database logging can adversely affect long-running automated processes, such as long-running data imports.</span></span>

### <a name="best-practices"></a><span data-ttu-id="4f261-127">Najlepsze praktyki</span><span class="sxs-lookup"><span data-stu-id="4f261-127">Best practices</span></span>

<span data-ttu-id="4f261-128">Aby poprawić wydajność, ogranicz wpisy dziennika, wybierając określone pola do zapisania zamiast całych tabel.</span><span class="sxs-lookup"><span data-stu-id="4f261-128">To improve performance, limit log entries by selecting specific fields to log instead of whole tables.</span></span> <span data-ttu-id="4f261-129">W celu zapewnienia ogólnej wydajności rejestrowanie w bazie danych jest ograniczone do 20 tabel.</span><span class="sxs-lookup"><span data-stu-id="4f261-129">To help maintain overall performance, database logging is limited to 20 tables.</span></span>

> [!NOTE]
> <span data-ttu-id="4f261-130">Można rejestrować tylko aktualizacje dla poszczególnych pól.</span><span class="sxs-lookup"><span data-stu-id="4f261-130">Only updates can be logged for individual fields.</span></span>

## <a name="set-up-database-logging"></a><span data-ttu-id="4f261-131">Konfigurowanie rejestrowania bazy danych</span><span class="sxs-lookup"><span data-stu-id="4f261-131">Set up database logging</span></span>

<span data-ttu-id="4f261-132">Aby skonfigurować rejestrowanie bazy danych, można skorzystać z kreatora **Rejestracji zmian w bazie danych**.</span><span class="sxs-lookup"><span data-stu-id="4f261-132">You can use the **Logging database changes** wizard to set up database logging.</span></span> <span data-ttu-id="4f261-133">Kreator stanowi elastyczny sposób konfigurowania rejestrowania tabel lub pól.</span><span class="sxs-lookup"><span data-stu-id="4f261-133">The wizard provides a flexible way to set up logging for tables or fields.</span></span>

1. <span data-ttu-id="4f261-134">Przejdź do **Administrowanie systemem > Łącza > Baza danych > Ustawienia dziennika bazy danych**.</span><span class="sxs-lookup"><span data-stu-id="4f261-134">Go to **System administration > Links > Database > Database log setup**.</span></span> <span data-ttu-id="4f261-135">Wybierz opcję **Nowy**, aby uruchomić kreatora **Rejestracji zmian w bazie danych**.</span><span class="sxs-lookup"><span data-stu-id="4f261-135">Select **New** to start the **Logging database changes** wizard.</span></span>
2. <span data-ttu-id="4f261-136">Wykonaj czynności w kreatorze.</span><span class="sxs-lookup"><span data-stu-id="4f261-136">Complete the wizard.</span></span>

## <a name="clean-up-database-logs"></a><span data-ttu-id="4f261-137">Oczyszczanie dzienników bazy danych</span><span class="sxs-lookup"><span data-stu-id="4f261-137">Clean up database logs</span></span>

<span data-ttu-id="4f261-138">Można usunąć wszystkie dzienniki bazy danych lub ich część, korzystając z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="4f261-138">You can delete all or part of the database logs, using the following options:</span></span>

- <span data-ttu-id="4f261-139">Umożliwia wybór wszystkich dzienników dla określonej tabeli.</span><span class="sxs-lookup"><span data-stu-id="4f261-139">Select all logs for a particular table.</span></span>
- <span data-ttu-id="4f261-140">Wybierz określone typy dziennika bazy danych.</span><span class="sxs-lookup"><span data-stu-id="4f261-140">Select specific types of database log.</span></span>
- <span data-ttu-id="4f261-141">Umożliwia wybranie daty i godziny utworzenia dziennika.</span><span class="sxs-lookup"><span data-stu-id="4f261-141">Select a date and time that a log was created.</span></span>

<span data-ttu-id="4f261-142">Aby skonfigurować czyszczenie dziennika bazy danych, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="4f261-142">To set up database log cleanup, follow these steps:</span></span> 

1. <span data-ttu-id="4f261-143">Przejdź do **Administrowanie systemem > Łącza > Baza danych > Dziennik bazy danych**.</span><span class="sxs-lookup"><span data-stu-id="4f261-143">Go to **System administration > Links > Database > Database log**.</span></span> <span data-ttu-id="4f261-144">Wybierz opcję **Oczyszczanie dziennika**.</span><span class="sxs-lookup"><span data-stu-id="4f261-144">Select **Clean up log**.</span></span>

2. <span data-ttu-id="4f261-145">Wybierz metodę wybierania dzienników do usunięcia, wprowadzając jedną z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="4f261-145">Choose a method of selecting logs to delete by entering one of the following options:</span></span>

   - <span data-ttu-id="4f261-146">ID tabeli</span><span class="sxs-lookup"><span data-stu-id="4f261-146">Table ID</span></span>
   - <span data-ttu-id="4f261-147">Typ dziennika</span><span class="sxs-lookup"><span data-stu-id="4f261-147">Type of log</span></span>
   - <span data-ttu-id="4f261-148">Data i godzina utworzenia</span><span class="sxs-lookup"><span data-stu-id="4f261-148">Created date and time</span></span>

3. <span data-ttu-id="4f261-149">Karta **Czyszczenie dziennika bazy danych** umożliwia określenie, kiedy ma być wykonywane zadanie oczyszczania dziennika.</span><span class="sxs-lookup"><span data-stu-id="4f261-149">Use the **Database log cleanup** tab to determine when to run the log cleanup task.</span></span> <span data-ttu-id="4f261-150">Domyślnie dzienniki bazy danych są dostępne przez 30 dni.</span><span class="sxs-lookup"><span data-stu-id="4f261-150">By default, database logs are available for 30 days.</span></span>
