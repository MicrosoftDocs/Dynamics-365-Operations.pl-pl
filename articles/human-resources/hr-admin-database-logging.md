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
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ae974436469c00a3df6fd40d9d60521a0883a917
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054819"
---
# <a name="configure-and-manage-database-logging"></a><span data-ttu-id="72f74-103">Konfigurowanie i zarządzanie rejestrowaniem bazy danych</span><span class="sxs-lookup"><span data-stu-id="72f74-103">Configure and manage database logging</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="72f74-104">Można śledzić zmiany w tabelach i polach w Dynamics 365 Human Resources z rejestrowaniem w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="72f74-104">You can track changes to tables and fields in Dynamics 365 Human Resources with database logging.</span></span> <span data-ttu-id="72f74-105">W tym temacie opisano sposób:</span><span class="sxs-lookup"><span data-stu-id="72f74-105">This topic describes how to:</span></span>

- <span data-ttu-id="72f74-106">Zarządzanie zabezpieczeniami i wydajnością dla rejestrowania w bazie danych</span><span class="sxs-lookup"><span data-stu-id="72f74-106">Manage security and performance for database logging</span></span>
- <span data-ttu-id="72f74-107">Konfigurowanie rejestrowania bazy danych</span><span class="sxs-lookup"><span data-stu-id="72f74-107">Set up database logging</span></span>
- <span data-ttu-id="72f74-108">Oczyszczanie dzienników bazy danych</span><span class="sxs-lookup"><span data-stu-id="72f74-108">Clean up database logs</span></span>

## <a name="overview-of-database-logging"></a><span data-ttu-id="72f74-109">Omówienie rejestrowania w bazie danych</span><span class="sxs-lookup"><span data-stu-id="72f74-109">Overview of database logging</span></span>

<span data-ttu-id="72f74-110">Można śledzić zmiany rejestrowania w bazie danych w tabelach i polach w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="72f74-110">Database logging tracks specific changes to Microsoft Dynamics 365 Human Resources tables and fields.</span></span> <span data-ttu-id="72f74-111">Te zmiany obejmują wstawianie, aktualizowanie lub usuwanie.</span><span class="sxs-lookup"><span data-stu-id="72f74-111">These changes include inserting, updating, or deleting.</span></span> <span data-ttu-id="72f74-112">Rejestrowanie w bazie danych zapisuje rekord zmian w tabelach lub polach w tabeli dziennika bazy danych.</span><span class="sxs-lookup"><span data-stu-id="72f74-112">Database logging stores a record of changes to tables or fields in the database log table.</span></span>

<span data-ttu-id="72f74-113">Do zastosowań biznesowych w rejestrowaniu bazy danych należą:</span><span class="sxs-lookup"><span data-stu-id="72f74-113">The business uses of database logging include:</span></span>

- <span data-ttu-id="72f74-114">Tworzenie rekordu inspekcji zmian w konkretnych tabelach zawierających poufne informacje.</span><span class="sxs-lookup"><span data-stu-id="72f74-114">Creating an audit record of changes to specific tables that contain sensitive information.</span></span>
- <span data-ttu-id="72f74-115">Śledzenie pojedynczych transakcji.</span><span class="sxs-lookup"><span data-stu-id="72f74-115">Tracking single transactions.</span></span> <span data-ttu-id="72f74-116">Rejestrowanie w bazie danych nie jest przeznaczone do śledzenia zautomatyzowanych transakcji uruchamianych w zadaniach wsadowych.</span><span class="sxs-lookup"><span data-stu-id="72f74-116">Database logging isn't intended for tracking automated transactions that run in batch jobs.</span></span>

## <a name="security-for-database-logging"></a><span data-ttu-id="72f74-117">Zabezpieczenia dotyczące rejestrowania w bazie danych</span><span class="sxs-lookup"><span data-stu-id="72f74-117">Security for database logging</span></span>

<span data-ttu-id="72f74-118">Dzienniki bazy danych mogą zawierać dane poufne.</span><span class="sxs-lookup"><span data-stu-id="72f74-118">Database logs can contain sensitive data.</span></span> <span data-ttu-id="72f74-119">Umożliwia ograniczenie dostępu, aby obejmował tylko role zabezpieczeń wymagające dostępu do danych dziennika.</span><span class="sxs-lookup"><span data-stu-id="72f74-119">Limit access to include only security roles that need access to the log data.</span></span>

## <a name="database-logging-and-performance"></a><span data-ttu-id="72f74-120">Rejestrowanie i wydajność bazy danych</span><span class="sxs-lookup"><span data-stu-id="72f74-120">Database logging and performance</span></span>

<span data-ttu-id="72f74-121">Podczas gdy wartość jest cenna od perspektywy biznesowej, rejestrowanie w bazie danych może być kosztowne w użyciu i zarządzaniu zasobami.</span><span class="sxs-lookup"><span data-stu-id="72f74-121">While valuable from a business perspective, database logging can be expensive in resource use and management.</span></span> <span data-ttu-id="72f74-122">Wpływ rejestrowania bazy danych na wydajność obejmuje:</span><span class="sxs-lookup"><span data-stu-id="72f74-122">The performance implications of database logging include:</span></span>

- <span data-ttu-id="72f74-123">Tabela dziennika bazy danych może szybko rosnąć i powodować zwiększenie rozmiaru bazy danych.</span><span class="sxs-lookup"><span data-stu-id="72f74-123">The database log table can grow quickly and cause an increase in the size of the database.</span></span> <span data-ttu-id="72f74-124">Wzrost zależy od ilości zarejestrowanych danych, które mają zostać zachowane.</span><span class="sxs-lookup"><span data-stu-id="72f74-124">Growth depends on the amount of logged data that you decide to keep.</span></span> <span data-ttu-id="72f74-125">Domyślnie tabela dziennika bazy danych obsługuje tylko 30 dni danych dziennika.</span><span class="sxs-lookup"><span data-stu-id="72f74-125">By default, the database log table maintains only 30 days of log data.</span></span> 

- <span data-ttu-id="72f74-126">Rejestrowanie bazy danych może niekorzystnie wpłynąć na długotrwałe procesy, takie jak długotrwałe importowanie danych.</span><span class="sxs-lookup"><span data-stu-id="72f74-126">Database logging can adversely affect long-running automated processes, such as long-running data imports.</span></span>

### <a name="best-practices"></a><span data-ttu-id="72f74-127">Najlepsze praktyki</span><span class="sxs-lookup"><span data-stu-id="72f74-127">Best practices</span></span>

<span data-ttu-id="72f74-128">Aby poprawić wydajność, ogranicz wpisy dziennika, wybierając określone pola do zapisania zamiast całych tabel.</span><span class="sxs-lookup"><span data-stu-id="72f74-128">To improve performance, limit log entries by selecting specific fields to log instead of whole tables.</span></span> <span data-ttu-id="72f74-129">W celu zapewnienia ogólnej wydajności rejestrowanie w bazie danych jest ograniczone do 20 tabel.</span><span class="sxs-lookup"><span data-stu-id="72f74-129">To help maintain overall performance, database logging is limited to 20 tables.</span></span>

> [!NOTE]
> <span data-ttu-id="72f74-130">Można rejestrować tylko aktualizacje dla poszczególnych pól.</span><span class="sxs-lookup"><span data-stu-id="72f74-130">Only updates can be logged for individual fields.</span></span>

## <a name="set-up-database-logging"></a><span data-ttu-id="72f74-131">Konfigurowanie rejestrowania bazy danych</span><span class="sxs-lookup"><span data-stu-id="72f74-131">Set up database logging</span></span>

<span data-ttu-id="72f74-132">Aby skonfigurować rejestrowanie bazy danych, można skorzystać z kreatora **Rejestracji zmian w bazie danych**.</span><span class="sxs-lookup"><span data-stu-id="72f74-132">You can use the **Logging database changes** wizard to set up database logging.</span></span> <span data-ttu-id="72f74-133">Kreator stanowi elastyczny sposób konfigurowania rejestrowania tabel lub pól.</span><span class="sxs-lookup"><span data-stu-id="72f74-133">The wizard provides a flexible way to set up logging for tables or fields.</span></span>

1. <span data-ttu-id="72f74-134">Przejdź do **Administrowanie systemem > Łącza > Baza danych > Ustawienia dziennika bazy danych**.</span><span class="sxs-lookup"><span data-stu-id="72f74-134">Go to **System administration > Links > Database > Database log setup**.</span></span> <span data-ttu-id="72f74-135">Wybierz opcję **Nowy**, aby uruchomić kreatora **Rejestracji zmian w bazie danych**.</span><span class="sxs-lookup"><span data-stu-id="72f74-135">Select **New** to start the **Logging database changes** wizard.</span></span>
2. <span data-ttu-id="72f74-136">Wybierz pozycję **Następny**.</span><span class="sxs-lookup"><span data-stu-id="72f74-136">Select **Next**.</span></span> 
3. <span data-ttu-id="72f74-137">Na stronie **Tabele i pola** kreatora wybierz tabele i pola, w których chcesz włączyć rejestrowanie bazy danych, i wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="72f74-137">On the **Tables and fields** page of the wizard, select the the tables and fields on which you want to enable database logging, and select **Next**.</span></span>

   > [!Note]
   > <span data-ttu-id="72f74-138">Rejestrowanie bazy danych nie jest dostępne we wszystkich tabelach w bazie danych Zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="72f74-138">Database logging is not available on all tables in the Human Resources database.</span></span> <span data-ttu-id="72f74-139">Wybranie opcji **Pokaż wszystkie tabele** pod listą spowoduje rozwinięcie listy tabel i pól w celu pokazania wszystkich tabel baz danych, dla których jest dostępne rejestrowanie bazy danych, ale będzie to podzestaw pełnej listy tabel bazy danych.</span><span class="sxs-lookup"><span data-stu-id="72f74-139">Selecting **Show all tables** below the list expands the list of tables and fields to show all database tables for which database logging is available, but this will be a subset of the full list of database tables.</span></span>

4. <span data-ttu-id="72f74-140">Na stronie **Typy zmian** w kreatorze wybierz operacje na danych, dla których chcesz śledzić zmiany poszczególnych tabel i pól, a następnie wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="72f74-140">On the **Types of change** page of the wizard, select the data operations for which you want to track changes for each of the tables and fields, and select **Next**.</span></span> <span data-ttu-id="72f74-141">Opis operacji dotyczących danych dostępnych do rejestrowania znajduje się w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="72f74-141">See the table below for a description of the data operations that are available for logging.</span></span>
5. <span data-ttu-id="72f74-142">Na stronie **Zakończ** przejrzyj zmiany, które zostaną wprowadzone, i wybierz przycisk **Zakończ**.</span><span class="sxs-lookup"><span data-stu-id="72f74-142">On the **Finish** page, review the changes that will be made, and select **Finish**.</span></span>

| <span data-ttu-id="72f74-143">Operacja</span><span class="sxs-lookup"><span data-stu-id="72f74-143">Operation</span></span> | <span data-ttu-id="72f74-144">opis</span><span class="sxs-lookup"><span data-stu-id="72f74-144">Description</span></span> |
| -- | -- |
| <span data-ttu-id="72f74-145">Śledź nowe transakcje</span><span class="sxs-lookup"><span data-stu-id="72f74-145">Track new transactions</span></span> | <span data-ttu-id="72f74-146">Utwórz dziennik dla nowych rekordów, które są tworzone w tabeli.</span><span class="sxs-lookup"><span data-stu-id="72f74-146">Create a log for new records that are created in the table.</span></span> |
| <span data-ttu-id="72f74-147">Aktualizowanie</span><span class="sxs-lookup"><span data-stu-id="72f74-147">Update</span></span> | <span data-ttu-id="72f74-148">Umożliwia tworzenie dziennika aktualizacji rekordów tabeli lub aktualizacji pojedynczych pól w tabeli.</span><span class="sxs-lookup"><span data-stu-id="72f74-148">Create a log for updates to table records, or updates to individually selected fields in the table.</span></span> <span data-ttu-id="72f74-149">Jeśli użytkownik wybierze opcję rejestrować aktualizacje tabeli, po każdym zaktualizowaniu dowolnego pola rekordu w tabeli tworzony jest rekord dziennika.</span><span class="sxs-lookup"><span data-stu-id="72f74-149">If you select to log updates for the table, then a log record is created each time an update is made to any field of any record on the table.</span></span> <span data-ttu-id="72f74-150">Jeśli użytkownik wybierze opcję rejestrować aktualizacje określonych pól, rekord dziennika jest tworzony tylko podczas aktualizacji tych pól rekordów tabel.</span><span class="sxs-lookup"><span data-stu-id="72f74-150">If you select to log updates for specific fields, then a log record is created only when updates are made to those fields of table records.</span></span> |
| <span data-ttu-id="72f74-151">Usuwanie</span><span class="sxs-lookup"><span data-stu-id="72f74-151">Delete</span></span> | <span data-ttu-id="72f74-152">Utwórz dziennik dla rekordów usuniętych z tabeli.</span><span class="sxs-lookup"><span data-stu-id="72f74-152">Create a log for records deleted from the table.</span></span> |
| <span data-ttu-id="72f74-153">Klucz zmiany nazwy</span><span class="sxs-lookup"><span data-stu-id="72f74-153">Rename key</span></span> | <span data-ttu-id="72f74-154">Utwórz rekord dziennika po zmianie nazwy klucza tabeli.</span><span class="sxs-lookup"><span data-stu-id="72f74-154">Create a log record when a table key is renamed.</span></span> |


## <a name="clean-up-database-logs"></a><span data-ttu-id="72f74-155">Oczyszczanie dzienników bazy danych</span><span class="sxs-lookup"><span data-stu-id="72f74-155">Clean up database logs</span></span>

<span data-ttu-id="72f74-156">Można usunąć wszystkie dzienniki bazy danych lub ich część, korzystając z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="72f74-156">You can delete all or part of the database logs, using the following options:</span></span>

- <span data-ttu-id="72f74-157">Umożliwia wybór wszystkich dzienników dla określonej tabeli.</span><span class="sxs-lookup"><span data-stu-id="72f74-157">Select all logs for a particular table.</span></span>
- <span data-ttu-id="72f74-158">Wybierz określone typy dziennika bazy danych.</span><span class="sxs-lookup"><span data-stu-id="72f74-158">Select specific types of database log.</span></span>
- <span data-ttu-id="72f74-159">Umożliwia wybranie daty i godziny utworzenia dziennika.</span><span class="sxs-lookup"><span data-stu-id="72f74-159">Select a date and time that a log was created.</span></span>

<span data-ttu-id="72f74-160">Aby skonfigurować czyszczenie dziennika bazy danych, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="72f74-160">To set up database log cleanup, follow these steps:</span></span> 

1. <span data-ttu-id="72f74-161">Przejdź do **Administrowanie systemem > Łącza > Baza danych > Dziennik bazy danych**.</span><span class="sxs-lookup"><span data-stu-id="72f74-161">Go to **System administration > Links > Database > Database log**.</span></span> <span data-ttu-id="72f74-162">Wybierz opcję **Oczyszczanie dziennika**.</span><span class="sxs-lookup"><span data-stu-id="72f74-162">Select **Clean up log**.</span></span>

2. <span data-ttu-id="72f74-163">Wybierz metodę wybierania dzienników do usunięcia, wprowadzając jedną z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="72f74-163">Choose a method of selecting logs to delete by entering one of the following options:</span></span>

   - <span data-ttu-id="72f74-164">ID tabeli</span><span class="sxs-lookup"><span data-stu-id="72f74-164">Table ID</span></span>
   - <span data-ttu-id="72f74-165">Typ dziennika</span><span class="sxs-lookup"><span data-stu-id="72f74-165">Type of log</span></span>
   - <span data-ttu-id="72f74-166">Data i godzina utworzenia</span><span class="sxs-lookup"><span data-stu-id="72f74-166">Created date and time</span></span>

3. <span data-ttu-id="72f74-167">Karta **Czyszczenie dziennika bazy danych** umożliwia określenie, kiedy ma być wykonywane zadanie oczyszczania dziennika.</span><span class="sxs-lookup"><span data-stu-id="72f74-167">Use the **Database log cleanup** tab to determine when to run the log cleanup task.</span></span> <span data-ttu-id="72f74-168">Domyślnie dzienniki bazy danych są dostępne przez 30 dni.</span><span class="sxs-lookup"><span data-stu-id="72f74-168">By default, database logs are available for 30 days.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
