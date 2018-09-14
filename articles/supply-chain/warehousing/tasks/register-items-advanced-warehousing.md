--- 
title: "Rejestrowanie elementów dla zaawansowanego magazynowania za pomocą arkusza przyjęć towarów"
description: "W tej procedurze pokazano sposób rejestrowania towarów za pomocą arkusza przyjęcia towaru, gdy jest używany zaawansowany proces zarządzania magazynem."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 392884d2a87c10a5f38bf6f51967f879c68c1ca6
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a><span data-ttu-id="3fd26-103">Rejestrowanie elementów dla zaawansowanego magazynowania za pomocą arkusza przyjęć towarów</span><span class="sxs-lookup"><span data-stu-id="3fd26-103">Register items for an advanced warehousing enabled item using an item arrival journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3fd26-104">W tej procedurze pokazano sposób rejestrowania towarów za pomocą arkusza przyjęcia towaru, gdy jest używany zaawansowany proces zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="3fd26-104">This procedure shows you how to register items using the item arrival journal when you are using advanced warehouse management processes.</span></span> <span data-ttu-id="3fd26-105">Zazwyczaj wykonuje to pracownik przyjmujący.</span><span class="sxs-lookup"><span data-stu-id="3fd26-105">This would usually be done by a receiving clerk.</span></span> 

<span data-ttu-id="3fd26-106">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="3fd26-106">You can run this procedure in demo data company USMF, or on your own data.</span></span> <span data-ttu-id="3fd26-107">Przed rozpoczęciem wykonywania zadań z przewodnika musisz mieć potwierdzone zamówienie zakupu z otwartym wierszem zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="3fd26-107">You need to have a confirmed purchase order with an open purchase order line before you start this guide.</span></span> <span data-ttu-id="3fd26-108">Towar w wierszu musi być magazynowy, nie może używać wariantów produktu i nie może mieć wymiarów śledzenia.</span><span class="sxs-lookup"><span data-stu-id="3fd26-108">The item on the line must be stocked, and it must not use product variants, and must not have tracking dimensions.</span></span> <span data-ttu-id="3fd26-109">Towar musi być także skojarzony z grupą wymiarów magazynowania, która obsługuje proces zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="3fd26-109">And the item needs to be associated with a warehouse management process enabled storage dimension group.</span></span> <span data-ttu-id="3fd26-110">Używany magazyn musi mieć włączoną obsługę procesów zarządzania magazynem, a lokalizacji używana dla przyjęć musi być kontrolowana przez numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="3fd26-110">The warehouse that’s used must be enabled for warehouse management processes and the location that you use for receiving must be license plate controlled.</span></span> <span data-ttu-id="3fd26-111">Jeśli używasz firmy USMF, można użyć firmy 1001, magazynu 51 i towaru M9200, aby utworzyć zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="3fd26-111">If you’re using USMF, you can use company account 1001, Warehouse 51, and item M9200 to create your PO.</span></span> 

<span data-ttu-id="3fd26-112">Zapisz numer tworzonego zamówienia zakupu, a także numer towaru i oddział użyte w wierszu zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="3fd26-112">Make a note of the number of the purchase order that you create, and also note the item number and the site that you used for your purchase order line.</span></span>


## <a name="create-an-item-arrival-journal-header"></a><span data-ttu-id="3fd26-113">Tworzenie nagłówka arkusza przyjęcia towaru</span><span class="sxs-lookup"><span data-stu-id="3fd26-113">Create an item arrival journal header</span></span>
1. <span data-ttu-id="3fd26-114">Przejdź do okna Przyjęcie towaru.</span><span class="sxs-lookup"><span data-stu-id="3fd26-114">Go to Item arrival.</span></span>
2. <span data-ttu-id="3fd26-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3fd26-115">Click New.</span></span>
3. <span data-ttu-id="3fd26-116">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3fd26-116">In the Name field, type a value.</span></span>
    * <span data-ttu-id="3fd26-117">Jeśli używasz firmy USMF, możesz wpisać WHS.</span><span class="sxs-lookup"><span data-stu-id="3fd26-117">If you are using USMF, you can type WHS.</span></span> <span data-ttu-id="3fd26-118">Jeśli korzystasz z innych danych, to arkusz, którego nazwę wybierzesz, musi mieć następujące właściwości: w polu Sprawdzanie lokalizacji pobrania ustawiona wartość Nie oraz w polu Zarządzanie kwarantanną ustawiona wartość Nie.</span><span class="sxs-lookup"><span data-stu-id="3fd26-118">If you’re using other data, the journal whose name you choose has to have the following properties: Check picking location must be set to No, and Quarantine management must be set to No.</span></span>  
4. <span data-ttu-id="3fd26-119">W polu Numer wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3fd26-119">In the Number field, type a value.</span></span>
5. <span data-ttu-id="3fd26-120">W polu Oddział wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3fd26-120">In the Site field, type a value.</span></span>
    * <span data-ttu-id="3fd26-121">Wybierz oddział, który został użyty w wierszu zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="3fd26-121">Select the site that you used for your purchase order line.</span></span> <span data-ttu-id="3fd26-122">Będzie on służył jako wartość domyślna ustawiana we wszystkich wierszach w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="3fd26-122">This will serve as a default value, which will default to all lines in the journal.</span></span> <span data-ttu-id="3fd26-123">Jeśli użyto magazynu 51 z firmy USMF, wybierz oddział 5.</span><span class="sxs-lookup"><span data-stu-id="3fd26-123">If you used warehouse 51 in USMF, choose site 5.</span></span>  
6. <span data-ttu-id="3fd26-124">W polu Magazyn wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3fd26-124">In the Warehouse field, type a value.</span></span>
    * <span data-ttu-id="3fd26-125">Wybierz prawidłowy magazyn dla wybranego oddziału.</span><span class="sxs-lookup"><span data-stu-id="3fd26-125">Select a valid warehouse for the site that you’ve selected.</span></span> <span data-ttu-id="3fd26-126">Będzie on służył jako wartość domyślna ustawiana we wszystkich wierszach w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="3fd26-126">This will serve as a default value, which will default to all lines in the journal.</span></span> <span data-ttu-id="3fd26-127">Jeśli używasz przykładowych wartości z firmy USMF, wybierz magazyn 51.</span><span class="sxs-lookup"><span data-stu-id="3fd26-127">If you’re using the example values in USMF, select 51.</span></span>  
7. <span data-ttu-id="3fd26-128">W polu Lokalizacja wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3fd26-128">In the Location field, type a value.</span></span>
    * <span data-ttu-id="3fd26-129">Wybierz prawidłową lokalizację w wybranym magazynie.</span><span class="sxs-lookup"><span data-stu-id="3fd26-129">Select a valid location in the warehouse that you’ve selected.</span></span> <span data-ttu-id="3fd26-130">Lokalizacja musi być skojarzona z profilem lokalizacji, który jest kontrolowany przez numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="3fd26-130">The location has to be associated with a location profile, which is license plate controlled.</span></span> <span data-ttu-id="3fd26-131">Będzie on służył jako wartość domyślna ustawiana we wszystkich wierszach w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="3fd26-131">This will serve as a default value, which will default to all lines in the journal.</span></span> <span data-ttu-id="3fd26-132">Jeśli używasz przykładowych wartości z firmy USMF, wybierz lokalizację Bulk-008.</span><span class="sxs-lookup"><span data-stu-id="3fd26-132">If you’re using the example values in USMF, select Bulk-008.</span></span>  
8. <span data-ttu-id="3fd26-133">Kliknij prawym przyciskiem myszy strzałkę rozwijaną w polu Numer identyfikacyjny i wybierz polecenie Wyświetl szczegóły.</span><span class="sxs-lookup"><span data-stu-id="3fd26-133">Right-click on the drop-down arrow in the License plate field and then select View details.</span></span>
9. <span data-ttu-id="3fd26-134">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3fd26-134">Click New.</span></span>
10. <span data-ttu-id="3fd26-135">W polu Numer identyfikacyjny wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3fd26-135">In the License plate field, type a value.</span></span>
    * <span data-ttu-id="3fd26-136">Zanotuj wartość.</span><span class="sxs-lookup"><span data-stu-id="3fd26-136">Make a note of the value.</span></span>  
11. <span data-ttu-id="3fd26-137">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3fd26-137">Click Save.</span></span>
12. <span data-ttu-id="3fd26-138">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3fd26-138">Close the page.</span></span>
13. <span data-ttu-id="3fd26-139">W polu Numer identyfikacyjny wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3fd26-139">In the License plate field, type a value.</span></span>
    * <span data-ttu-id="3fd26-140">Wprowadź wartość utworzonego właśnie numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="3fd26-140">Enter the value of the license plate that you just created.</span></span> <span data-ttu-id="3fd26-141">Będzie on służył jako wartość domyślna ustawiana we wszystkich wierszach w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="3fd26-141">This will serve as a default value, which will default to all lines in the journal.</span></span>  
14. <span data-ttu-id="3fd26-142">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3fd26-142">Click OK.</span></span>

## <a name="add-a-line"></a><span data-ttu-id="3fd26-143">Dodawanie wiersza</span><span class="sxs-lookup"><span data-stu-id="3fd26-143">Add a line</span></span>
1. <span data-ttu-id="3fd26-144">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="3fd26-144">Click Add line.</span></span>
2. <span data-ttu-id="3fd26-145">W polu Numer towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3fd26-145">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="3fd26-146">Wprowadź numer towaru użyty w wierszu zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="3fd26-146">Enter the item number that you used on the purchase order line.</span></span>  
3. <span data-ttu-id="3fd26-147">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="3fd26-147">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="3fd26-148">Wprowadź ilość, jaką chcesz zarejestrować.</span><span class="sxs-lookup"><span data-stu-id="3fd26-148">Enter the quantity that you want to register.</span></span>  
    * <span data-ttu-id="3fd26-149">Pole Data określa dzień, kiedy dostępna ilość tego towaru zostanie zarejestrowana w magazynie.</span><span class="sxs-lookup"><span data-stu-id="3fd26-149">The Date field determines the date on which the on-hand quantity of this item will be registered in the inventory.</span></span>  
    * <span data-ttu-id="3fd26-150">Pole Identyfikator partii zostanie wypełnione przez system, jeśli można je unikatowo zidentyfikować na podstawie dostarczonych informacji.</span><span class="sxs-lookup"><span data-stu-id="3fd26-150">The lot ID will be populated by the system if it can be uniquely identified from the information provided.</span></span> <span data-ttu-id="3fd26-151">W przeciwnym razie należy go dodać ręcznie.</span><span class="sxs-lookup"><span data-stu-id="3fd26-151">Otherwise you will have to add this manually.</span></span> <span data-ttu-id="3fd26-152">To pole jest wymagane i łączy tę rejestrację z określonym wierszem dokumentu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="3fd26-152">This is a mandatory field, which links this registration to a specific source document line.</span></span>  

## <a name="complete-the-registration"></a><span data-ttu-id="3fd26-153">Rejestrowanie</span><span class="sxs-lookup"><span data-stu-id="3fd26-153">Complete the registration</span></span>
1. <span data-ttu-id="3fd26-154">Kliknij przycisk Sprawdź poprawność.</span><span class="sxs-lookup"><span data-stu-id="3fd26-154">Click Validate.</span></span>
    * <span data-ttu-id="3fd26-155">Spowoduje to sprawdzenie, czy arkusz jest gotowy do zaksięgowania.</span><span class="sxs-lookup"><span data-stu-id="3fd26-155">This checks that the journal is ready to be posted.</span></span> <span data-ttu-id="3fd26-156">Jeżeli weryfikacja przyniesie wynik negatywny, trzeba naprawić błędy, zanim będzie można zaksięgować arkusz.</span><span class="sxs-lookup"><span data-stu-id="3fd26-156">If the validation fails you will need to fix the errors before you can post the journal.</span></span>  
2. <span data-ttu-id="3fd26-157">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3fd26-157">Click OK.</span></span>
    * <span data-ttu-id="3fd26-158">Po kliknięciu przycisku OK sprawdź pasek komunikatów.</span><span class="sxs-lookup"><span data-stu-id="3fd26-158">After you clicked OK, check the message.</span></span> <span data-ttu-id="3fd26-159">Powinien tam być komunikat z informacją, że arkusz jest poprawny.</span><span class="sxs-lookup"><span data-stu-id="3fd26-159">There should be a message saying that the journal is OK.</span></span>  
3. <span data-ttu-id="3fd26-160">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="3fd26-160">Click Post.</span></span>
4. <span data-ttu-id="3fd26-161">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3fd26-161">Click OK.</span></span>
    * <span data-ttu-id="3fd26-162">Po kliknięciu przycisku OK sprawdź pasek komunikatów.</span><span class="sxs-lookup"><span data-stu-id="3fd26-162">After you have clicked OK, check the message bar.</span></span> <span data-ttu-id="3fd26-163">Powinien tam być komunikat z informacją, że operacja została wykonana.</span><span class="sxs-lookup"><span data-stu-id="3fd26-163">There should be a message saying that the operation completed.</span></span>  
5. <span data-ttu-id="3fd26-164">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3fd26-164">Close the page.</span></span>


