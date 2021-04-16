---
title: Konfigurowanie i zarządzanie rejestrowaniem bazy danych
description: Można śledzić zmiany w tabelach i polach w Dynamics 365 Human Resources z rejestrowaniem w bazie danych.
author: andreabichsel
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: d22ff9f3ce68c81f37840342c795d7d162eb027b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801342"
---
# <a name="configure-and-manage-database-logging"></a><span data-ttu-id="e129f-103">Konfigurowanie i zarządzanie rejestrowaniem bazy danych</span><span class="sxs-lookup"><span data-stu-id="e129f-103">Configure and manage database logging</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e129f-104">Można śledzić zmiany w tabelach i polach w Dynamics 365 Human Resources z rejestrowaniem w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="e129f-104">You can track changes to tables and fields in Dynamics 365 Human Resources with database logging.</span></span> <span data-ttu-id="e129f-105">W tym temacie opisano sposób:</span><span class="sxs-lookup"><span data-stu-id="e129f-105">This topic describes how to:</span></span>

- <span data-ttu-id="e129f-106">Zarządzanie zabezpieczeniami i wydajnością dla rejestrowania w bazie danych</span><span class="sxs-lookup"><span data-stu-id="e129f-106">Manage security and performance for database logging</span></span>
- <span data-ttu-id="e129f-107">Konfigurowanie rejestrowania bazy danych</span><span class="sxs-lookup"><span data-stu-id="e129f-107">Set up database logging</span></span>
- <span data-ttu-id="e129f-108">Oczyszczanie dzienników bazy danych</span><span class="sxs-lookup"><span data-stu-id="e129f-108">Clean up database logs</span></span>

## <a name="overview-of-database-logging"></a><span data-ttu-id="e129f-109">Omówienie rejestrowania w bazie danych</span><span class="sxs-lookup"><span data-stu-id="e129f-109">Overview of database logging</span></span>

<span data-ttu-id="e129f-110">Można śledzić zmiany rejestrowania w bazie danych w tabelach i polach w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e129f-110">Database logging tracks specific changes to Microsoft Dynamics 365 Human Resources tables and fields.</span></span> <span data-ttu-id="e129f-111">Te zmiany obejmują wstawianie, aktualizowanie lub usuwanie.</span><span class="sxs-lookup"><span data-stu-id="e129f-111">These changes include inserting, updating, or deleting.</span></span> <span data-ttu-id="e129f-112">Rejestrowanie w bazie danych zapisuje rekord zmian w tabelach lub polach w tabeli dziennika bazy danych.</span><span class="sxs-lookup"><span data-stu-id="e129f-112">Database logging stores a record of changes to tables or fields in the database log table.</span></span>

<span data-ttu-id="e129f-113">Do zastosowań biznesowych w rejestrowaniu bazy danych należą:</span><span class="sxs-lookup"><span data-stu-id="e129f-113">The business uses of database logging include:</span></span>

- <span data-ttu-id="e129f-114">Tworzenie rekordu inspekcji zmian w konkretnych tabelach zawierających poufne informacje.</span><span class="sxs-lookup"><span data-stu-id="e129f-114">Creating an audit record of changes to specific tables that contain sensitive information.</span></span>
- <span data-ttu-id="e129f-115">Śledzenie pojedynczych transakcji.</span><span class="sxs-lookup"><span data-stu-id="e129f-115">Tracking single transactions.</span></span> <span data-ttu-id="e129f-116">Rejestrowanie w bazie danych nie jest przeznaczone do śledzenia zautomatyzowanych transakcji uruchamianych w zadaniach wsadowych.</span><span class="sxs-lookup"><span data-stu-id="e129f-116">Database logging isn't intended for tracking automated transactions that run in batch jobs.</span></span>

## <a name="security-for-database-logging"></a><span data-ttu-id="e129f-117">Zabezpieczenia dotyczące rejestrowania w bazie danych</span><span class="sxs-lookup"><span data-stu-id="e129f-117">Security for database logging</span></span>

<span data-ttu-id="e129f-118">Dzienniki bazy danych mogą zawierać dane poufne.</span><span class="sxs-lookup"><span data-stu-id="e129f-118">Database logs can contain sensitive data.</span></span> <span data-ttu-id="e129f-119">Umożliwia ograniczenie dostępu, aby obejmował tylko role zabezpieczeń wymagające dostępu do danych dziennika.</span><span class="sxs-lookup"><span data-stu-id="e129f-119">Limit access to include only security roles that need access to the log data.</span></span>

## <a name="database-logging-and-performance"></a><span data-ttu-id="e129f-120">Rejestrowanie i wydajność bazy danych</span><span class="sxs-lookup"><span data-stu-id="e129f-120">Database logging and performance</span></span>

<span data-ttu-id="e129f-121">Podczas gdy wartość jest cenna od perspektywy biznesowej, rejestrowanie w bazie danych może być kosztowne w użyciu i zarządzaniu zasobami.</span><span class="sxs-lookup"><span data-stu-id="e129f-121">While valuable from a business perspective, database logging can be expensive in resource use and management.</span></span> <span data-ttu-id="e129f-122">Wpływ rejestrowania bazy danych na wydajność obejmuje:</span><span class="sxs-lookup"><span data-stu-id="e129f-122">The performance implications of database logging include:</span></span>

- <span data-ttu-id="e129f-123">Tabela dziennika bazy danych może szybko rosnąć i powodować zwiększenie rozmiaru bazy danych.</span><span class="sxs-lookup"><span data-stu-id="e129f-123">The database log table can grow quickly and cause an increase in the size of the database.</span></span> <span data-ttu-id="e129f-124">Wzrost zależy od ilości zarejestrowanych danych, które mają zostać zachowane.</span><span class="sxs-lookup"><span data-stu-id="e129f-124">Growth depends on the amount of logged data that you decide to keep.</span></span> <span data-ttu-id="e129f-125">Domyślnie tabela dziennika bazy danych obsługuje tylko 30 dni danych dziennika.</span><span class="sxs-lookup"><span data-stu-id="e129f-125">By default, the database log table maintains only 30 days of log data.</span></span> 

- <span data-ttu-id="e129f-126">Rejestrowanie bazy danych może niekorzystnie wpłynąć na długotrwałe procesy, takie jak długotrwałe importowanie danych.</span><span class="sxs-lookup"><span data-stu-id="e129f-126">Database logging can adversely affect long-running automated processes, such as long-running data imports.</span></span>

### <a name="best-practices"></a><span data-ttu-id="e129f-127">Najlepsze praktyki</span><span class="sxs-lookup"><span data-stu-id="e129f-127">Best practices</span></span>

<span data-ttu-id="e129f-128">Aby poprawić wydajność, ogranicz wpisy dziennika, wybierając określone pola do zapisania zamiast całych tabel.</span><span class="sxs-lookup"><span data-stu-id="e129f-128">To improve performance, limit log entries by selecting specific fields to log instead of whole tables.</span></span> <span data-ttu-id="e129f-129">W celu zapewnienia ogólnej wydajności rejestrowanie w bazie danych jest ograniczone do 20 tabel.</span><span class="sxs-lookup"><span data-stu-id="e129f-129">To help maintain overall performance, database logging is limited to 20 tables.</span></span>

> [!NOTE]
> <span data-ttu-id="e129f-130">Można rejestrować tylko aktualizacje dla poszczególnych pól.</span><span class="sxs-lookup"><span data-stu-id="e129f-130">Only updates can be logged for individual fields.</span></span>

## <a name="set-up-database-logging"></a><span data-ttu-id="e129f-131">Konfigurowanie rejestrowania bazy danych</span><span class="sxs-lookup"><span data-stu-id="e129f-131">Set up database logging</span></span>

<span data-ttu-id="e129f-132">Aby skonfigurować rejestrowanie bazy danych, można skorzystać z kreatora **Rejestracji zmian w bazie danych**.</span><span class="sxs-lookup"><span data-stu-id="e129f-132">You can use the **Logging database changes** wizard to set up database logging.</span></span> <span data-ttu-id="e129f-133">Kreator stanowi elastyczny sposób konfigurowania rejestrowania tabel lub pól.</span><span class="sxs-lookup"><span data-stu-id="e129f-133">The wizard provides a flexible way to set up logging for tables or fields.</span></span>

1. <span data-ttu-id="e129f-134">Przejdź do **Administrowanie systemem > Łącza > Baza danych > Ustawienia dziennika bazy danych**.</span><span class="sxs-lookup"><span data-stu-id="e129f-134">Go to **System administration > Links > Database > Database log setup**.</span></span> <span data-ttu-id="e129f-135">Wybierz opcję **Nowy**, aby uruchomić kreatora **Rejestracji zmian w bazie danych**.</span><span class="sxs-lookup"><span data-stu-id="e129f-135">Select **New** to start the **Logging database changes** wizard.</span></span>
2. <span data-ttu-id="e129f-136">Wybierz pozycję **Następny**.</span><span class="sxs-lookup"><span data-stu-id="e129f-136">Select **Next**.</span></span> 
3. <span data-ttu-id="e129f-137">Na stronie **Tabele i pola** kreatora wybierz tabele i pola, w których chcesz włączyć rejestrowanie bazy danych, i wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="e129f-137">On the **Tables and fields** page of the wizard, select the the tables and fields on which you want to enable database logging, and select **Next**.</span></span>

   > [!Note]
   > <span data-ttu-id="e129f-138">Rejestrowanie bazy danych nie jest dostępne we wszystkich tabelach w bazie danych Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="e129f-138">Database logging is not available on all tables in the Human Resources database.</span></span> <span data-ttu-id="e129f-139">Wybranie opcji **Pokaż wszystkie tabele** pod listą spowoduje rozwinięcie listy tabel i pól w celu pokazania wszystkich tabel baz danych, dla których jest dostępne rejestrowanie bazy danych, ale będzie to podzestaw pełnej listy tabel bazy danych.</span><span class="sxs-lookup"><span data-stu-id="e129f-139">Selecting **Show all tables** below the list expands the list of tables and fields to show all database tables for which database logging is available, but this will be a subset of the full list of database tables.</span></span>

4. <span data-ttu-id="e129f-140">Na stronie **Typy zmian** w kreatorze wybierz operacje na danych, dla których chcesz śledzić zmiany poszczególnych tabel i pól, a następnie wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="e129f-140">On the **Types of change** page of the wizard, select the data operations for which you want to track changes for each of the tables and fields, and select **Next**.</span></span> <span data-ttu-id="e129f-141">Opis operacji dotyczących danych dostępnych do rejestrowania znajduje się w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="e129f-141">See the table below for a description of the data operations that are available for logging.</span></span>
5. <span data-ttu-id="e129f-142">Na stronie **Zakończ** przejrzyj zmiany, które zostaną wprowadzone, i wybierz przycisk **Zakończ**.</span><span class="sxs-lookup"><span data-stu-id="e129f-142">On the **Finish** page, review the changes that will be made, and select **Finish**.</span></span>

| <span data-ttu-id="e129f-143">Operacja</span><span class="sxs-lookup"><span data-stu-id="e129f-143">Operation</span></span> | <span data-ttu-id="e129f-144">opis</span><span class="sxs-lookup"><span data-stu-id="e129f-144">Description</span></span> |
| -- | -- |
| <span data-ttu-id="e129f-145">Śledź nowe transakcje</span><span class="sxs-lookup"><span data-stu-id="e129f-145">Track new transactions</span></span> | <span data-ttu-id="e129f-146">Utwórz dziennik dla nowych rekordów, które są tworzone w tabeli.</span><span class="sxs-lookup"><span data-stu-id="e129f-146">Create a log for new records that are created in the table.</span></span> |
| <span data-ttu-id="e129f-147">Aktualizowanie</span><span class="sxs-lookup"><span data-stu-id="e129f-147">Update</span></span> | <span data-ttu-id="e129f-148">Umożliwia tworzenie dziennika aktualizacji rekordów tabeli lub aktualizacji pojedynczych pól w tabeli.</span><span class="sxs-lookup"><span data-stu-id="e129f-148">Create a log for updates to table records, or updates to individually selected fields in the table.</span></span> <span data-ttu-id="e129f-149">Jeśli użytkownik wybierze opcję rejestrować aktualizacje tabeli, po każdym zaktualizowaniu dowolnego pola rekordu w tabeli tworzony jest rekord dziennika.</span><span class="sxs-lookup"><span data-stu-id="e129f-149">If you select to log updates for the table, then a log record is created each time an update is made to any field of any record on the table.</span></span> <span data-ttu-id="e129f-150">Jeśli użytkownik wybierze opcję rejestrować aktualizacje określonych pól, rekord dziennika jest tworzony tylko podczas aktualizacji tych pól rekordów tabel.</span><span class="sxs-lookup"><span data-stu-id="e129f-150">If you select to log updates for specific fields, then a log record is created only when updates are made to those fields of table records.</span></span> |
| <span data-ttu-id="e129f-151">Usuwanie</span><span class="sxs-lookup"><span data-stu-id="e129f-151">Delete</span></span> | <span data-ttu-id="e129f-152">Utwórz dziennik dla rekordów usuniętych z tabeli.</span><span class="sxs-lookup"><span data-stu-id="e129f-152">Create a log for records deleted from the table.</span></span> |
| <span data-ttu-id="e129f-153">Klucz zmiany nazwy</span><span class="sxs-lookup"><span data-stu-id="e129f-153">Rename key</span></span> | <span data-ttu-id="e129f-154">Utwórz rekord dziennika po zmianie nazwy klucza tabeli.</span><span class="sxs-lookup"><span data-stu-id="e129f-154">Create a log record when a table key is renamed.</span></span> |


## <a name="clean-up-database-logs"></a><span data-ttu-id="e129f-155">Oczyszczanie dzienników bazy danych</span><span class="sxs-lookup"><span data-stu-id="e129f-155">Clean up database logs</span></span>

<span data-ttu-id="e129f-156">Można usunąć wszystkie dzienniki bazy danych lub ich część, korzystając z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="e129f-156">You can delete all or part of the database logs, using the following options:</span></span>

- <span data-ttu-id="e129f-157">Umożliwia wybór wszystkich dzienników dla określonej tabeli.</span><span class="sxs-lookup"><span data-stu-id="e129f-157">Select all logs for a particular table.</span></span>
- <span data-ttu-id="e129f-158">Wybierz określone typy dziennika bazy danych.</span><span class="sxs-lookup"><span data-stu-id="e129f-158">Select specific types of database log.</span></span>
- <span data-ttu-id="e129f-159">Umożliwia wybranie daty i godziny utworzenia dziennika.</span><span class="sxs-lookup"><span data-stu-id="e129f-159">Select a date and time that a log was created.</span></span>

<span data-ttu-id="e129f-160">Aby skonfigurować czyszczenie dziennika bazy danych, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="e129f-160">To set up database log cleanup, follow these steps:</span></span> 

1. <span data-ttu-id="e129f-161">Przejdź do **Administrowanie systemem > Łącza > Baza danych > Dziennik bazy danych**.</span><span class="sxs-lookup"><span data-stu-id="e129f-161">Go to **System administration > Links > Database > Database log**.</span></span> <span data-ttu-id="e129f-162">Wybierz opcję **Oczyszczanie dziennika**.</span><span class="sxs-lookup"><span data-stu-id="e129f-162">Select **Clean up log**.</span></span>

2. <span data-ttu-id="e129f-163">Wybierz metodę wybierania dzienników do usunięcia, wprowadzając jedną z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="e129f-163">Choose a method of selecting logs to delete by entering one of the following options:</span></span>

   - <span data-ttu-id="e129f-164">ID tabeli</span><span class="sxs-lookup"><span data-stu-id="e129f-164">Table ID</span></span>
   - <span data-ttu-id="e129f-165">Typ dziennika</span><span class="sxs-lookup"><span data-stu-id="e129f-165">Type of log</span></span>
   - <span data-ttu-id="e129f-166">Data i godzina utworzenia</span><span class="sxs-lookup"><span data-stu-id="e129f-166">Created date and time</span></span>

3. <span data-ttu-id="e129f-167">Karta **Czyszczenie dziennika bazy danych** umożliwia określenie, kiedy ma być wykonywane zadanie oczyszczania dziennika.</span><span class="sxs-lookup"><span data-stu-id="e129f-167">Use the **Database log cleanup** tab to determine when to run the log cleanup task.</span></span> <span data-ttu-id="e129f-168">Domyślnie dzienniki bazy danych są dostępne przez 30 dni.</span><span class="sxs-lookup"><span data-stu-id="e129f-168">By default, database logs are available for 30 days.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
