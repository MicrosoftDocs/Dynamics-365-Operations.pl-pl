---
title: Rozumienie pól Data i Godzina
description: Opis oczekiwań podczas używania pól daty i godziny w rozwiązaniu Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b7e5726f7e4beea1584b9a8e142212531ba1db56
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051744"
---
# <a name="understand-date-and-time-fields"></a><span data-ttu-id="550f9-103">Opis pól Data i Godzina</span><span class="sxs-lookup"><span data-stu-id="550f9-103">Understand Date and Time fields</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="550f9-104">**Pola daty i godziny** stanowią podstawową koncepcję w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="550f9-104">**Date and Time** fields are a fundamental concept in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="550f9-105">Ważne jest, aby zrozumieć sposób pracy z danymi **Daty i godziny** w formularzach Dataverse i źródłach zewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="550f9-105">It's important to understand how to work with **Date and Time** data in forms, Dataverse, and external sources.</span></span>

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a><span data-ttu-id="550f9-106">Opis różnicy między typami danych pól daty oraz daty i godziny</span><span class="sxs-lookup"><span data-stu-id="550f9-106">Understanding the difference between Date and Date and Time field data types</span></span>

<span data-ttu-id="550f9-107">Pola **Data i godzina** zawierają informacje o strefie czasowej, natomiast pola **Data** nie.</span><span class="sxs-lookup"><span data-stu-id="550f9-107">**Date and Time** fields contain time zone information, while **Date** fields don't.</span></span> <span data-ttu-id="550f9-108">Pola **Data** zawierają te same informacje w dowolnej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="550f9-108">**Date** fields display the same information in any location.</span></span> <span data-ttu-id="550f9-109">Wprowadzenie daty w polu **Data** powoduje, że Human Resources zapisuje tę samą datę do bazy danych.</span><span class="sxs-lookup"><span data-stu-id="550f9-109">When you enter a date into a **Date** field, Human Resources writes that same date to the database.</span></span>

<span data-ttu-id="550f9-110">W przypadku wyświetlania danych w polu **Data i Godzina** Human Resources dostosowuje datę i godzinę na podstawie konfiguracji strefy czasowej użytkownika w formularzu **Opcje użytkownika** (**Wspólne > Ustawienia > Opcje użytkownika**).</span><span class="sxs-lookup"><span data-stu-id="550f9-110">When displaying data in a **Date and Time** field, Human Resources adjusts the date and time based on the user's time zone set in the **User Options** form (**Common > Setup > User Options**).</span></span> <span data-ttu-id="550f9-111">Data i godzina wprowadzona w polu mogą być inne niż informacje zapisane w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="550f9-111">The date and time information you enter in the field might not be the same as the information written to the database.</span></span>

<span data-ttu-id="550f9-112">[![Formularz Opcje użytkownika](./media/useroptionsform.png)](./media/useroptionsform.png)</span><span class="sxs-lookup"><span data-stu-id="550f9-112">[![User options form](./media/useroptionsform.png)](./media/useroptionsform.png)</span></span>

## <a name="understanding-date-and-time-fields-in-forms"></a><span data-ttu-id="550f9-113">Rozumienie użycia pól Data i Godzina w formularzach</span><span class="sxs-lookup"><span data-stu-id="550f9-113">Understanding Date and Time fields in forms</span></span> 

<span data-ttu-id="550f9-114">W polu **Data i Godzina**, dane wyświetlane na ekranie nie są takie same jak dane przechowywane w bazie danych, jeśli strefa czasowa użytkownika nie jest ustawiona na Uniwersalny czas koordynowany (UTC).</span><span class="sxs-lookup"><span data-stu-id="550f9-114">**Date and Time** data displayed on the screen isn't the same as the data stored in the database if the user's time zone isn't set to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="550f9-115">Dane w polach **Data i godzina** są zawsze zapisywane jako czas UTC.</span><span class="sxs-lookup"><span data-stu-id="550f9-115">Data in **Date and Time** fields is always stored as UTC.</span></span>

<span data-ttu-id="550f9-116">[![Formularz pracownika UTC](./media/worker-form.png)](./media/worker-form.png)</span><span class="sxs-lookup"><span data-stu-id="550f9-116">[![Worker form UTC](./media/worker-form.png)](./media/worker-form.png)</span></span>

## <a name="understand-date-and-time-fields-in-the-database"></a><span data-ttu-id="550f9-117">Rozumienie użycia pól Data i Godzina w bazie danych</span><span class="sxs-lookup"><span data-stu-id="550f9-117">Understand Date and Time fields in the database</span></span> 

<span data-ttu-id="550f9-118">Gdy Human Resources zapisuje wartość **Data i godzina** w bazie danych, zapisuje dane w formacie UTC.</span><span class="sxs-lookup"><span data-stu-id="550f9-118">When Human Resources writes a **Date and Time** value to the database, it stores the data in UTC.</span></span> <span data-ttu-id="550f9-119">Umożliwia to użytkownikom wyświetlanie wszelkich danych dotyczących **Data i godzina** w odniesieniu do stref czasowych zdefiniowanych w opcjach użytkownika.</span><span class="sxs-lookup"><span data-stu-id="550f9-119">This allows users to see any **Date and Time** data relative to the time zone defined in their user options.</span></span>
 
<span data-ttu-id="550f9-120">W powyższym przykładzie czas rozpoczęcia to punkt w czasie, a nie określona data.</span><span class="sxs-lookup"><span data-stu-id="550f9-120">In the example above, the start time is a point in time, not a particular date.</span></span> <span data-ttu-id="550f9-121">Zmiana strefy czasowej zalogowanego użytkownika z poziomu GMT +12:00 na GMT UTC powoduje, że ten sam rekord pokazuje dane w formacie 04/30/2019 12:00:00 zamiast 05/01/2019 12:00:00.</span><span class="sxs-lookup"><span data-stu-id="550f9-121">By changing the time zone of the logged in user from GMT +12:00 to GMT UTC, the same record shows 04/30/2019 12:00:00 instead of 05/01/2019 12:00:00.</span></span>
  
<span data-ttu-id="550f9-122">W poniższym przykładzie zatrudnienie pracownika nr. 000724 staje się aktywne w tym samym czasie, niezależnie od strefy czasowej.</span><span class="sxs-lookup"><span data-stu-id="550f9-122">In the example below, employee 000724’s employment becomes active at the same time regardless of time zone.</span></span> <span data-ttu-id="550f9-123">Pracownik będzie aktywny w dniu 04/30/2019 w strefie czasowej GMT, który jest taki sam jak 05/01/2019 w strefie GMT +12:00.</span><span class="sxs-lookup"><span data-stu-id="550f9-123">The employee will be active on 04/30/2019 in the GMT time zone, which is the same as 05/01/2019 in GMT+12:00 time zone.</span></span> <span data-ttu-id="550f9-124">Odnoszą się do tego samego punktu w czasie, a nie do określonej daty.</span><span class="sxs-lookup"><span data-stu-id="550f9-124">Both refer to the same point in time and not a particular date.</span></span> 

<span data-ttu-id="550f9-125">[![Formularz pracownika GMT](./media/worker-form2.png)](./media/worker-form2.png)</span><span class="sxs-lookup"><span data-stu-id="550f9-125">[![Worker form GMT](./media/worker-form2.png)](./media/worker-form2.png)</span></span>

## <a name="date-and-time-data-in-data-management-framework-excel-dataverse-and-power-bi"></a><span data-ttu-id="550f9-126">Dane daty i godziny w strukturze zarządzania danymi, Excel, Dataverse i Power BI</span><span class="sxs-lookup"><span data-stu-id="550f9-126">Date and Time data in Data Management Framework, Excel, Dataverse, and Power BI</span></span> 

<span data-ttu-id="550f9-127">Środowisko zarządzania danymi, dodatek programu Excel, Dataverse i raportowanie Power BI są przeznaczone do interakcji z danymi bezpośrednio na poziomie bazy danych.</span><span class="sxs-lookup"><span data-stu-id="550f9-127">The Data Management Framework, Excel Add-In, Dataverse, and Power BI reporting are all designed to interact with data directly on the database level.</span></span> <span data-ttu-id="550f9-128">Ponieważ nie istnieje klient, który dostosowuje dane **Data i godzina** do strefy czasowej użytkownika, wszystkie wartości **Data i godzina** są w formacie UTC, co może prowadzić do niektórych nieprawidłowych założeń podczas wprowadzania lub wyświetlania danych.</span><span class="sxs-lookup"><span data-stu-id="550f9-128">Since there's no client to adjust **Date and Time** data to the time zone of the user, all **Date and Time** values are in UTC, which can lead to some incorrect assumptions when entering or viewing data.</span></span>  
 
<span data-ttu-id="550f9-129">Dane **Data i godzina** przesłane za pośrednictwem DMF, programu Excel lub Dataverse są uznawane przez bazę danych w formacie UTC.</span><span class="sxs-lookup"><span data-stu-id="550f9-129">**Date and Time** data submitted via DMF, Excel, or Dataverse is assumed to be in UTC by the database.</span></span> <span data-ttu-id="550f9-130">Może to spowodować pomyłkę w przypadku, gdy przesłana wartość **Data i godzina** nie zostanie wyświetlona w oczekiwany sposób, ponieważ użytkownik wyświetlający dane nie ma ustawionej czasu UTC dla danej strefy czasowej użytkownika.</span><span class="sxs-lookup"><span data-stu-id="550f9-130">This can cause some confusion when the submitted **Date and Time** value doesn't display as expected because the user viewing the data doesn't have their user time zone  set to UTC.</span></span> 
 
<span data-ttu-id="550f9-131">Podczas eksportowania danych ten sam element może mieć stan odwrotny.</span><span class="sxs-lookup"><span data-stu-id="550f9-131">The same thing can happen in reverse when data is exported.</span></span> <span data-ttu-id="550f9-132">Dane **Data i godzina** w wyeksportowanej jednostce DMF mogą być różne w zależności od tego, co jest wyświetlane w kliencie systemu Dynamics.</span><span class="sxs-lookup"><span data-stu-id="550f9-132">The **Date and Time** data in the exported DMF entity can be different than what is displayed in the Dynamics client.</span></span> 
 
<span data-ttu-id="550f9-133">W przypadku używania źródeł zewnętrznych, takich jak DMF do wyświetlania lub tworzenia danych, należy pamiętać, że wartości **Data i godzina** są uwzględniane domyślnie w formacie UTC, niezależnie od strefy czasowej komputera użytkownika lub jego bieżących ustawień strefy czasowej użytkownika.</span><span class="sxs-lookup"><span data-stu-id="550f9-133">When using external sources like DMF to view or author data, keep in mind that the **Date and Time** values are considered by default to be in UTC regardless of the time zone of the user's computer or their current user time zone settings.</span></span> 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a><span data-ttu-id="550f9-134">Przykłady tego samego rekordu wyświetlanego w różnych obszarach produktów</span><span class="sxs-lookup"><span data-stu-id="550f9-134">Examples of the same record being displayed in different product areas</span></span> 

<span data-ttu-id="550f9-135">**Human Resources ze strefą czasową użytkownika ustawioną jako UTC**</span><span class="sxs-lookup"><span data-stu-id="550f9-135">**Human Resources with user time zone set to UTC**</span></span>

<span data-ttu-id="550f9-136">[![Formularz pracownika ustawiony na czas UTC](./media/worker-form3.png)](./media/worker-form3.png)</span><span class="sxs-lookup"><span data-stu-id="550f9-136">[![Worker form set to UTC](./media/worker-form3.png)](./media/worker-form3.png)</span></span>

<span data-ttu-id="550f9-137">**Human Resources ze strefą czasową użytkownika ustawioną jako GMT +12:00**</span><span class="sxs-lookup"><span data-stu-id="550f9-137">**Human Resources with user time zone set to GMT +12:00**</span></span> 

<span data-ttu-id="550f9-138">[![Formularz pracownika ustawiony na czas GMT](./media/worker-form4.png)](./media/worker-form4.png)</span><span class="sxs-lookup"><span data-stu-id="550f9-138">[![Worker form set to GMT](./media/worker-form4.png)](./media/worker-form4.png)</span></span>

<span data-ttu-id="550f9-139">**Excel za pośrednictwem protokołu OData**</span><span class="sxs-lookup"><span data-stu-id="550f9-139">**Excel Via OData**</span></span>

<span data-ttu-id="550f9-140">[![Excel za pośrednictwem protokołu OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span><span class="sxs-lookup"><span data-stu-id="550f9-140">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span></span>

<span data-ttu-id="550f9-141">**Ustawianie DMF**</span><span class="sxs-lookup"><span data-stu-id="550f9-141">**DMF Staging**</span></span>

<span data-ttu-id="550f9-142">[![Ustawianie DMF](./media/DMFStaging.png)](./media/DMFStaging.png)</span><span class="sxs-lookup"><span data-stu-id="550f9-142">[![DMF Staging](./media/DMFStaging.png)](./media/DMFStaging.png)</span></span>

<span data-ttu-id="550f9-143">**Eksportowanie DMF**</span><span class="sxs-lookup"><span data-stu-id="550f9-143">**DMF Export**</span></span>

<span data-ttu-id="550f9-144">[![Eksportowanie DMF](./media/DMFexport.png)](./media/DMFexport.png)</span><span class="sxs-lookup"><span data-stu-id="550f9-144">[![DMF Export](./media/DMFexport.png)](./media/DMFexport.png)</span></span>

<span data-ttu-id="550f9-145">**Excel za pośrednictwem Dataverse**</span><span class="sxs-lookup"><span data-stu-id="550f9-145">**Excel via Dataverse**</span></span>

<span data-ttu-id="550f9-146">[![Excel za pośrednictwem Dataverse](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span><span class="sxs-lookup"><span data-stu-id="550f9-146">[![Excel via Dataverse](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span></span>

## <a name="see-also"></a><span data-ttu-id="550f9-147">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="550f9-147">See also</span></span>

[<span data-ttu-id="550f9-148">Dane daty i godziny</span><span class="sxs-lookup"><span data-stu-id="550f9-148">Date and time data</span></span>](/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[<span data-ttu-id="550f9-149">Preferowana strefa czasowa użytkownika</span><span class="sxs-lookup"><span data-stu-id="550f9-149">User preferred time zones</span></span>](/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]