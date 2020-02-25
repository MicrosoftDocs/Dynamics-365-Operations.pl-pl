---
title: Kalendarze czasu pracy
description: W tym temacie opisano funkcjonalność kalendarzy czasu pracy w programie Dynamics 365 Human Resources oraz sposób konfigurowania kalendarzy.
author: andreabichsel
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-07-01
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: ac19fca407bd936cb9b7edcfa9f4eb81daf607dd
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006225"
---
# <a name="working-time-calendars"></a><span data-ttu-id="d3892-103">Kalendarze czasu pracy</span><span class="sxs-lookup"><span data-stu-id="d3892-103">Working time calendars</span></span>

<span data-ttu-id="d3892-104">Funkcja kalendarza czasu pracy pozwala utworzyć kalendarz z godzinami i dniami, kiedy pracownicy pracują w organizacji.</span><span class="sxs-lookup"><span data-stu-id="d3892-104">The working time calendar enables you to create a calendar with the hours and days that employees work in your organization.</span></span> <span data-ttu-id="d3892-105">Kalendarze usprawniają obsługę wniosków o czas wolny dzięki domyślnemu rozpoznawaniu godzin i dni.</span><span class="sxs-lookup"><span data-stu-id="d3892-105">Calendars streamline the time off request process by default in the hours or days.</span></span> <span data-ttu-id="d3892-106">Gdy pracownik przesyła wniosek o czas wolny, nie musi się martwić o święta i dni wolne od pracy, ponieważ automatycznie zarządza tym kalendarz czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="d3892-106">When an employee submits a time off request, they don't have to worry about holidays and closures, which is handled for them through the working time calendar.</span></span>

## <a name="setting-up-a-working-time-calendar"></a><span data-ttu-id="d3892-107">Konfigurowanie kalendarza czasu pracy</span><span class="sxs-lookup"><span data-stu-id="d3892-107">Setting up a working time calendar</span></span>

<span data-ttu-id="d3892-108">Kalendarze zawierają informacje o generowaniu, wnioskowanych dniach i godzinach, dniach kalendarzowych, czasach pracy w dniach oraz zarejestrowanych pracownikach.</span><span class="sxs-lookup"><span data-stu-id="d3892-108">Calendars include generation details, the days and hours you want to included, the days of the calendar, working times for those days as well as enrolled employees.</span></span> 

<span data-ttu-id="d3892-109">Aby skonfigurować kalendarz, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="d3892-109">To set up a calendar, follow these steps:</span></span>

1. <span data-ttu-id="d3892-110">Na stronie **Administrowanie organizacją** kliknij opcję **Kalendarze**.</span><span class="sxs-lookup"><span data-stu-id="d3892-110">On the **Organization Administration** page, click **Calendars**.</span></span>

2. <span data-ttu-id="d3892-111">W okienku akcji kliknij przycisk **Nowy**, a następnie wprowadź nazwę i opis.</span><span class="sxs-lookup"><span data-stu-id="d3892-111">On the Action Pane, select **New** and enter a name and description.</span></span>

3. <span data-ttu-id="d3892-112">Wybierz dni pracy w organizacji i wprowadź czas pracy.</span><span class="sxs-lookup"><span data-stu-id="d3892-112">Choose the work days for your organization and enter work time.</span></span>

4. <span data-ttu-id="d3892-113">Dodaj święta i dni wolne od pracy za pomocą przycisku **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="d3892-113">Add Holidays and closures by using the **Add** button.</span></span>

5. <span data-ttu-id="d3892-114">Wprowadź nazwę i opis dla świąt i dni wolnych od pracy, taką jak Święta amerykańskie lub Dni wolne.</span><span class="sxs-lookup"><span data-stu-id="d3892-114">Enter the name and description for the holidays and closures, such as US holidays or Bank holidays.</span></span> <span data-ttu-id="d3892-115">Wprowadź daty świąt i dni wolnych od pracy.</span><span class="sxs-lookup"><span data-stu-id="d3892-115">Enter the dates for the holidays and closures.</span></span> <span data-ttu-id="d3892-116">Zapisz listę świąt i dni wolnych od pracy, a następnie zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d3892-116">Save the Holidays and closures list and close the page.</span></span>

6. <span data-ttu-id="d3892-117">Wybierz listę świąt i dni wolnych od pracy z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="d3892-117">Select the holidays and closures list from the drop-down menu.</span></span>

7. <span data-ttu-id="d3892-118">Jeśli pracownicy mają standardowo przewidziany czas wolny od pracy, na przykład przerwy na obiady i odpoczynek, dodaj je również.</span><span class="sxs-lookup"><span data-stu-id="d3892-118">If your employees have non-work time, such as lunches or breaks, add those as well.</span></span> <span data-ttu-id="d3892-119">Zaznacz opcję **Czas wolny od pracy**, a następnie wprowadź nazwę i przedział czasu.</span><span class="sxs-lookup"><span data-stu-id="d3892-119">Select **Non-work time** and enter the name and time range.</span></span> <span data-ttu-id="d3892-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d3892-120">Close the page.</span></span> 

8. <span data-ttu-id="d3892-121">Kliknij przycisk **Dodaj**, aby dodać czas wolny od pracy do kalendarza.</span><span class="sxs-lookup"><span data-stu-id="d3892-121">Click **Add** to add the non-work time to your calendar.</span></span>

9. <span data-ttu-id="d3892-122">Na karcie **Dni** wybierz opcję **Generuj**, aby wygenerować dni w kalendarzu.</span><span class="sxs-lookup"><span data-stu-id="d3892-122">On the **Days** tab, select **Generate** to generate the days in your calendar.</span></span> <span data-ttu-id="d3892-123">Wprowadź przedział dat kalendarza.</span><span class="sxs-lookup"><span data-stu-id="d3892-123">Enter the date range for the calendar.</span></span> <span data-ttu-id="d3892-124">Dni i czasy pracy zostaną wygenerowane na podstawie dni i czasów pracy zdefiniowanych w opcjach generowania powiązanych z wybranymi datami.</span><span class="sxs-lookup"><span data-stu-id="d3892-124">The days and working times are generated based on the work days and times defined under the generation options in conjunction with the dates selected.</span></span>

10. <span data-ttu-id="d3892-125">Aby przypisać kalendarz do pracowników, w okienku akcji wybierz opcję **Przypisz do pracowników etatowych**.</span><span class="sxs-lookup"><span data-stu-id="d3892-125">To assign a calendar to employees, select **Assign to employees** in the Action Pane.</span></span> <span data-ttu-id="d3892-126">Zaznacz pracowników, którym chcesz przypisać ten kalendarz, i kliknij przycisk **Przypisz**.</span><span class="sxs-lookup"><span data-stu-id="d3892-126">Select the that employees you would like to assign this calendar to, and then click **Assign**.</span></span>

<span data-ttu-id="d3892-127">Pracownicy nie muszą mieć przypisanych kalendarzy.</span><span class="sxs-lookup"><span data-stu-id="d3892-127">Employees aren't required to have calendars assigned.</span></span> <span data-ttu-id="d3892-128">Jeśli zdefiniowano kalendarz czasu pracy, dni wolne są automatycznie wykluczane z wniosku o czas wolny.</span><span class="sxs-lookup"><span data-stu-id="d3892-128">If there is a working time calendar defined, off days are automatically excluded from the request.</span></span> <span data-ttu-id="d3892-129">Ilość w godzinach lub dniach jest domyślnie ustawiana według czasów pracy określonych w kalendarzu.</span><span class="sxs-lookup"><span data-stu-id="d3892-129">The amount, in hours or days, defaults to the working times defined in the calendar.</span></span> <span data-ttu-id="d3892-130">Jeśli pracownik nie ma przypisanego kalendarza, wszystkie dni są dostępne dla przyznania czasu wolnego, a ilość czasu wolnego nie jest domyślna dla wniosku.</span><span class="sxs-lookup"><span data-stu-id="d3892-130">If an employee doesn't have a calendar assigned, all days are available for time off and the amount of time off is not the default for the request.</span></span> 
