---
title: Pracuj z ustawieniami daty i godziny w Microsoft Dynamics 365 for Talent
description: Opis oczekiwań podczas używania pól daty i godziny w rozwiązaniu Microsoft Dynamics 365 for Talent. Umożliwia uzyskanie jasności Dynamics 365 for Talent, co ma być oczekiwane podczas interakcji z danymi daty i godziny w formularzu, zewnętrznym źródle lub w Common Data Service.
author: Darinkramer
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-06-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b4c652992272ed1a5aecbb4c78f0d11f077149d1
ms.sourcegitcommit: 46bded82aa072adfedcf443629c2adc69f512c09
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/26/2019
ms.locfileid: "1791226"
---
# <a name="date-and-time-fields-in-talent"></a><span data-ttu-id="c44bb-104">Pola Data i Godzina w aplikacji Talent</span><span class="sxs-lookup"><span data-stu-id="c44bb-104">Date and Time fields in Talent</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c44bb-105">**Pola daty i godziny** stanowią podstawową koncepcję w Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="c44bb-105">**Date and Time** fields are a fundamental concept in Dynamics 365 for Talent.</span></span> <span data-ttu-id="c44bb-106">Ważne jest, aby zrozumieć sposób pracy z danymi **Daty i godziny** w formularzu Dynamics 365, Common Data Service i źródłach zewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="c44bb-106">It's important to understand how to work with **Date and Time** data in a Dynamics 365 form, Common Data Service, and external sources.</span></span>

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a><span data-ttu-id="c44bb-107">Opis różnicy między typami danych pól daty oraz daty i godziny</span><span class="sxs-lookup"><span data-stu-id="c44bb-107">Understanding the difference between Date and Date and Time field data types</span></span>

<span data-ttu-id="c44bb-108">Pola **Data i godzina** zawierają informacje o strefie czasowej, natomiast pola **Data** nie.</span><span class="sxs-lookup"><span data-stu-id="c44bb-108">**Date and Time** fields contain time zone information, while **Date** fields don't.</span></span> <span data-ttu-id="c44bb-109">Pola **Data** zawierają te same informacje w dowolnej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c44bb-109">**Date** fields display the same information in any location.</span></span> <span data-ttu-id="c44bb-110">Wprowadzenie daty w polu **Data** powoduje, że Talent zapisuje tę samą datę do bazy danych.</span><span class="sxs-lookup"><span data-stu-id="c44bb-110">When you enter a date into a **Date** field, Talent writes that same date to the database.</span></span>

<span data-ttu-id="c44bb-111">W przypadku wyświetlania danych w polu **Data i Godzina** Talent dostosowuje datę i godzinę na podstawie konfiguracji strefy czasowej użytkownika w formularzu **Opcje użytkownika** (**Wspólne > Ustawienia > Opcje użytkownika**).</span><span class="sxs-lookup"><span data-stu-id="c44bb-111">When displaying data in a **Date and Time** field, Talent adjusts the date and time based on the user's time zone set in the **User Options** form (**Common > Setup > User Options**).</span></span> <span data-ttu-id="c44bb-112">Data i godzina wprowadzona w polu mogą być inne niż informacje zapisane w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="c44bb-112">The date and time information you enter in the field might not be the same as the information written to the database.</span></span>

<span data-ttu-id="c44bb-113">[![Formularz Opcje użytkownika](./media/useroptionsform.png)](./media/useroptionsform.png)</span><span class="sxs-lookup"><span data-stu-id="c44bb-113">[![User options form](./media/useroptionsform.png)](./media/useroptionsform.png)</span></span>

## <a name="understanding-date-and-time-fields-in-forms"></a><span data-ttu-id="c44bb-114">Rozumienie użycia pól Data i Godzina w formularzach</span><span class="sxs-lookup"><span data-stu-id="c44bb-114">Understanding Date and Time fields in forms</span></span> 

<span data-ttu-id="c44bb-115">Podczas wprowadzania danych w polu **Data i Godzina**, dane wyświetlane na ekranie nie są takie same jak dane przechowywane w bazie danych, jeśli strefa czasowa użytkownika nie jest ustawiona na Uniwersalny czas koordynowany (UTC).</span><span class="sxs-lookup"><span data-stu-id="c44bb-115">When entering data in a **Date and Time** field, the data displayed on the screen isn't the same as the data stored in the database if the user's time zone isn't set to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="c44bb-116">Dane w polach **Data i godzina** są zawsze zapisywane jako czas UTC.</span><span class="sxs-lookup"><span data-stu-id="c44bb-116">Data in **Date and Time** fields is always stored as UTC.</span></span>

<span data-ttu-id="c44bb-117">[![Formularz pracownika](./media/worker-form.png)](./media/worker-form.png)</span><span class="sxs-lookup"><span data-stu-id="c44bb-117">[![Worker form](./media/worker-form.png)](./media/worker-form.png)</span></span>

## <a name="understand-date-and-time-fields-in-the-database"></a><span data-ttu-id="c44bb-118">Rozumienie użycia pól Data i Godzina w bazie danych</span><span class="sxs-lookup"><span data-stu-id="c44bb-118">Understand Date and Time fields in the database</span></span> 

<span data-ttu-id="c44bb-119">Gdy Talent zapisuje wartość **Data i godzina** w bazie danych, zapisuje dane w formacie UTC.</span><span class="sxs-lookup"><span data-stu-id="c44bb-119">When Talent writes a **Date and time** value to the database, it stores the data in UTC.</span></span> <span data-ttu-id="c44bb-120">Umożliwia to użytkownikom wyświetlanie wszelkich danych dotyczących **Data i godzina** w odniesieniu do stref czasowych zdefiniowanych w opcjach użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c44bb-120">This allows users to see any **Date and Time** data relative to the time zone defined in their user options.</span></span>
 
<span data-ttu-id="c44bb-121">W powyższym przykładzie czas rozpoczęcia to punkt w czasie, a nie określona data.</span><span class="sxs-lookup"><span data-stu-id="c44bb-121">In the example above, the start time is a point in time, not a particular date.</span></span> <span data-ttu-id="c44bb-122">Zmiana strefy czasowej zalogowanego użytkownika z poziomu GMT +12:00 na GMT UTC powoduje, że ten sam rekord został utworzony w formacie 04/30/2019 12:00:00 zamiast 05/01/2019 12:00:00.</span><span class="sxs-lookup"><span data-stu-id="c44bb-122">By changing the time zone of the logged in user from GMT +12:00 to GMT UTC, the same record just created shows 04/30/2019 12:00:00 instead of 05/01/2019 12:00:00.</span></span>
  
<span data-ttu-id="c44bb-123">W poniższym przykładzie zatrudnienie pracownika nr. 000724 staje się aktywne w tym samym czasie, niezależnie od strefy czasowej.</span><span class="sxs-lookup"><span data-stu-id="c44bb-123">In the example below, employee 000724’s employment becomes active at the same time regardless of time zone.</span></span> <span data-ttu-id="c44bb-124">Pracownik będzie aktywny w dniu 04/30/2019 w strefie czasowej GMT, który jest taki sam jak 05/01/2019 w strefie GMT +12:00.</span><span class="sxs-lookup"><span data-stu-id="c44bb-124">The employee will be active on 04/30/2019 in the GMT time zone, which is the same as 05/01/2019 in GMT+12:00 time zone.</span></span> <span data-ttu-id="c44bb-125">Odnoszą się do tego samego punktu w czasie, a nie do określonej daty.</span><span class="sxs-lookup"><span data-stu-id="c44bb-125">Both refer to the same point in time and not a particular date.</span></span> 

<span data-ttu-id="c44bb-126">[![Formularz pracownika](./media/worker-form2.png)](./media/worker-form2.png)</span><span class="sxs-lookup"><span data-stu-id="c44bb-126">[![Worker form](./media/worker-form2.png)](./media/worker-form2.png)</span></span>

## <a name="date-and-time-data-in-data-management-framework-excel-common-data-service-and-power-bi"></a><span data-ttu-id="c44bb-127">Dane daty i godziny w strukturze zarządzania danymi, Excel, Common Data Service i Power BI</span><span class="sxs-lookup"><span data-stu-id="c44bb-127">Date and Time data in Data Management Framework, Excel, Common Data Service, and Power BI</span></span> 

<span data-ttu-id="c44bb-128">Środowisko zarządzania danymi, dodatek programu Excel, Common Data Service i raportowanie Power BI są przeznaczone do interakcji z danymi bezpośrednio na poziomie bazy danych.</span><span class="sxs-lookup"><span data-stu-id="c44bb-128">The Data Management Framework, Excel Add-In, Common Data Service, and Power BI reporting are all designed to interact with data directly on the database level.</span></span> <span data-ttu-id="c44bb-129">Ponieważ nie istnieje klient, który dostosowuje dane **Data i godzina** do strefy czasowej użytkownika, wszystkie wartości **Data i godzina** są w formacie UTC, co może prowadzić do niektórych nieprawidłowych założeń podczas wprowadzania lub wyświetlania danych.</span><span class="sxs-lookup"><span data-stu-id="c44bb-129">Since there is no client to adjust **Date and Time** data to the time zone of the user, all **Date and Time** values are in UTC, which can lead to some incorrect assumptions when entering or viewing data.</span></span>  
 
<span data-ttu-id="c44bb-130">Dane **Data i godzina** przesłane za pośrednictwem DMF, programu Excel lub Common Data Service są uznawane przez bazę danych w formacie UTC.</span><span class="sxs-lookup"><span data-stu-id="c44bb-130">**Date and Time** data that is submitted via DMF, Excel, or Common Data Service is assumed to be in UTC by the database.</span></span> <span data-ttu-id="c44bb-131">Może to spowodować pomyłkę w przypadku, gdy przesłana wartość **Data i godzina** nie zostanie wyświetlona w oczekiwany sposób, ponieważ użytkownik wyświetlający dane nie ma ustawionej czasu UTC dla danej strefy czasowej użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c44bb-131">This can cause some confusion when the submitted **Date and Time** value doesn't display as expected because the user viewing the data doesn't have their user time zone  set to UTC.</span></span> 
 
<span data-ttu-id="c44bb-132">Podczas eksportowania danych ten sam element może mieć stan odwrotny.</span><span class="sxs-lookup"><span data-stu-id="c44bb-132">The same thing can happen in reverse when data is exported.</span></span> <span data-ttu-id="c44bb-133">Dane **Data i godzina** w wyeksportowanej jednostce DMF mogą być różne w zależności od tego, co jest wyświetlane w kliencie systemu Dynamics.</span><span class="sxs-lookup"><span data-stu-id="c44bb-133">The **Date and Time** data in the exported DMF entity can be different then what is displayed in the Dynamics client.</span></span> 
 
<span data-ttu-id="c44bb-134">W przypadku używania źródeł zewnętrznych, takich jak DMF do wyświetlania lub tworzenia danych, należy pamiętać, że wartości **Data i godzina** są uwzględniane domyślnie w formacie UTC, niezależnie od strefy czasowej komputera użytkownika lub jego bieżących ustawień strefy czasowej użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c44bb-134">When using external sources like DMF to view or author data, it is important to keep in mind that the **Date and Time** values are considered by default to be in UTC regardless of the time zone of the user's computer or their current user time zone settings.</span></span> 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a><span data-ttu-id="c44bb-135">Przykłady tego samego rekordu wyświetlanego w różnych obszarach produktów</span><span class="sxs-lookup"><span data-stu-id="c44bb-135">Examples of the same record being displayed in different product areas</span></span> 

<span data-ttu-id="c44bb-136">**Talent ze strefą czasową użytkownika ustawioną jako UTC**</span><span class="sxs-lookup"><span data-stu-id="c44bb-136">**Talent with user time zone set to UTC**</span></span>

<span data-ttu-id="c44bb-137">[![Formularz pracownika](./media/worker-form3.png)](./media/worker-form3.png)</span><span class="sxs-lookup"><span data-stu-id="c44bb-137">[![Worker form](./media/worker-form3.png)](./media/worker-form3.png)</span></span>

<span data-ttu-id="c44bb-138">**Talent ze strefą czasową użytkownika ustawioną jako GMT +12:00**</span><span class="sxs-lookup"><span data-stu-id="c44bb-138">**Talent with user time zone set to GMT +12:00**</span></span> 

<span data-ttu-id="c44bb-139">[![Formularz pracownika](./media/worker-form4.png)](./media/worker-form4.png)</span><span class="sxs-lookup"><span data-stu-id="c44bb-139">[![Worker form](./media/worker-form4.png)](./media/worker-form4.png)</span></span>

<span data-ttu-id="c44bb-140">**Excel za pośrednictwem protokołu OData**</span><span class="sxs-lookup"><span data-stu-id="c44bb-140">**Excel Via OData**</span></span>

<span data-ttu-id="c44bb-141">[![Excel za pośrednictwem protokołu OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span><span class="sxs-lookup"><span data-stu-id="c44bb-141">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span></span>

<span data-ttu-id="c44bb-142">**Ustawianie DMF**</span><span class="sxs-lookup"><span data-stu-id="c44bb-142">**DMF Staging**</span></span>

<span data-ttu-id="c44bb-143">[![Ustawianie DMF](./media/DMFStaging.png)](./media/DMFStaging.png)</span><span class="sxs-lookup"><span data-stu-id="c44bb-143">[![DMF Staging](./media/DMFStaging.png)](./media/DMFStaging.png)</span></span>

<span data-ttu-id="c44bb-144">**Eksportowanie DMF**</span><span class="sxs-lookup"><span data-stu-id="c44bb-144">**DMF Export**</span></span>

<span data-ttu-id="c44bb-145">[![Ustawianie DMF](./media/DMFexport.png)](./media/DMFexport.png)</span><span class="sxs-lookup"><span data-stu-id="c44bb-145">[![DMF Staging](./media/DMFexport.png)](./media/DMFexport.png)</span></span>

<span data-ttu-id="c44bb-146">**Excel za pośrednictwem Common Data Service**</span><span class="sxs-lookup"><span data-stu-id="c44bb-146">**Excel via Common Data Service**</span></span>

<span data-ttu-id="c44bb-147">[![Excel za pośrednictwem Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span><span class="sxs-lookup"><span data-stu-id="c44bb-147">[![Excel via Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span></span>

### <a name="see-also"></a><span data-ttu-id="c44bb-148">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="c44bb-148">See also</span></span>

[<span data-ttu-id="c44bb-149">Dane daty i godziny</span><span class="sxs-lookup"><span data-stu-id="c44bb-149">Date and time data</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[<span data-ttu-id="c44bb-150">Preferowana strefa czasowa użytkownika</span><span class="sxs-lookup"><span data-stu-id="c44bb-150">User preferred time zones</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 
