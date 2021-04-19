---
title: Rejestrowanie pozycji dla włączonej pozycji zaawansowanego magazynowania za pomocą arkusza przyjęć towarów
description: W tym temacie pokazano sposób rejestrowania towarów za pomocą arkusza przyjęcia towaru, gdy jest używany zaawansowany proces zarządzania magazynem.
author: ShylaThompson
ms.date: 03/24/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c58aa1cec6c0bfe33fa1ef90267dcd8ac1218157
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830841"
---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a><span data-ttu-id="a44a7-103">Rejestrowanie pozycji dla włączonej pozycji zaawansowanego magazynowania za pomocą arkusza przyjęć towarów</span><span class="sxs-lookup"><span data-stu-id="a44a7-103">Register items for an advanced warehousing enabled item using an item arrival journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a44a7-104">W tym temacie pokazano sposób rejestrowania towarów za pomocą arkusza przyjęcia towaru, gdy jest używany zaawansowany proces zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="a44a7-104">This topic presents a scenario that shows how to register items using the item arrival journal when you are using advanced warehouse management processes.</span></span> <span data-ttu-id="a44a7-105">Zazwyczaj wykonuje to pracownik przyjmujący.</span><span class="sxs-lookup"><span data-stu-id="a44a7-105">This would usually be done by a receiving clerk.</span></span>

## <a name="enable-sample-data"></a><span data-ttu-id="a44a7-106">Włącz dane przykładowe</span><span class="sxs-lookup"><span data-stu-id="a44a7-106">Enable sample data</span></span>

<span data-ttu-id="a44a7-107">Aby przejść przez ten scenariusz, używając przykładowych rekordów i wartości określonych w tym temacie, musisz używać systemu, w którym są zainstalowane standardowe dane demonstracyjne, i przed rozpoczęciem musisz wybrać firmy *USMF*.</span><span class="sxs-lookup"><span data-stu-id="a44a7-107">To work through this scenario using the sample records and values specified in this topic, you must be using a system where the standard demo data is installed, and you must select the *USMF* legal entity before you begin.</span></span>

<span data-ttu-id="a44a7-108">Zamiast tego można przejść przez ten scenariusz, zastępując wartości z własnych danych, pod warunkiem że dostępne są następujące dane:</span><span class="sxs-lookup"><span data-stu-id="a44a7-108">You can instead work through this scenario by substituting values from your own data provided that you have the following data available:</span></span>

- <span data-ttu-id="a44a7-109">Musisz mieć potwierdzone zamówienie zakupu z otwartym wierszem zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="a44a7-109">You must have a confirmed purchase order with an open purchase order line.</span></span>
- <span data-ttu-id="a44a7-110">Towar w wierszu musi być magazynowany.</span><span class="sxs-lookup"><span data-stu-id="a44a7-110">The item on the line must be stocked.</span></span> <span data-ttu-id="a44a7-111">Nie może używać wariantów produktu i nie może mieć wymiarów śledzenia.</span><span class="sxs-lookup"><span data-stu-id="a44a7-111">It must not use product variants, and must not have tracking dimensions.</span></span>
- <span data-ttu-id="a44a7-112">Towar musi być skojarzony z grupą wymiarów magazynu, dla której jest włączony proces zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="a44a7-112">The item must be associated with a storage dimension group that has warehouse management process enabled.</span></span>
- <span data-ttu-id="a44a7-113">Używany magazyn musi mieć włączoną obsługę procesów zarządzania magazynem, a lokalizacji używana dla przyjęć musi być kontrolowana przez numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="a44a7-113">The warehouse that's used must be enabled for warehouse management processes and the location that you use for receiving must be license plate controlled.</span></span>

## <a name="create-an-item-arrival-journal-header-that-uses-warehouse-management"></a><span data-ttu-id="a44a7-114">Tworzenie nagłówka arkusza przybycia towaru, który korzysta z zarządzania magazynem</span><span class="sxs-lookup"><span data-stu-id="a44a7-114">Create an item arrival journal header that uses warehouse management</span></span>

<span data-ttu-id="a44a7-115">Poniższy scenariusz przedstawia sposób tworzenia nagłówka arkusza przybycia towaru, w którym jest używane zarządzanie magazynem:</span><span class="sxs-lookup"><span data-stu-id="a44a7-115">The following scenario shows how to create an item arrival journal header that uses warehouse management:</span></span>

1. <span data-ttu-id="a44a7-116">Upewnij się, że system zawiera potwierdzone zamówienie zakupu spełniające wymagania opisane w poprzedniej sekcji.</span><span class="sxs-lookup"><span data-stu-id="a44a7-116">Make sure your system contains a confirmed purchase order that fulfils the requirements outlined in the previous section.</span></span> <span data-ttu-id="a44a7-117">W tym scenariuszu jest używane zamówienie zakupu dla firmy *USMF*, konta dostawcy *1001*, magazynu *51*, z wierszem zamówienia dla *10 PL* (10 palet) numeru pozycji *M9200*.</span><span class="sxs-lookup"><span data-stu-id="a44a7-117">This scenario uses a purchase order for company *USMF*, vendor account *1001*, warehouse *51*, with an order line for *10 PL* (10 pallets) of item number *M9200*.</span></span>
1. <span data-ttu-id="a44a7-118">Zanotuj numer zamówienia zakupu do użycia.</span><span class="sxs-lookup"><span data-stu-id="a44a7-118">Make a note of the purchase order number that you will use.</span></span>
1. <span data-ttu-id="a44a7-119">Wybierz kolejno opcje **Zarządzanie zapasami \> Wpisy w arkuszu \> Przyjęcie towaru \> Przyjęcie towaru**.</span><span class="sxs-lookup"><span data-stu-id="a44a7-119">Go to **Inventory management \> Journal entries \> Item arrival \> Item arrival**.</span></span>
1. <span data-ttu-id="a44a7-120">Wybierz pozycję **Nowy** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="a44a7-120">Select **New** on the Action Pane.</span></span>
1. <span data-ttu-id="a44a7-121">Zostanie otwarte okno dialogowe **Tworzenie arkusza zarządzania magazynem**.</span><span class="sxs-lookup"><span data-stu-id="a44a7-121">The **Create warehouse management journal** dialog box opens.</span></span> <span data-ttu-id="a44a7-122">W polu **Nazwa** wybierz nazwę arkusza.</span><span class="sxs-lookup"><span data-stu-id="a44a7-122">Select a journal name in the **Name** field.</span></span>
    - <span data-ttu-id="a44a7-123">Jeśli używasz danych firmy demonstracyjnej *USMF*, wybierz opcję *WHS*.</span><span class="sxs-lookup"><span data-stu-id="a44a7-123">If you are using *USMF* sample data, select *WHS*.</span></span>
    - <span data-ttu-id="a44a7-124">Jeśli używasz własnych danych, wybierz arkusz musi mieć ustawienie **Sprawdź lokalizację pobrania** na *Nie* i opcję **Zarządzanie kwarantanną** na wartość *Nie*.</span><span class="sxs-lookup"><span data-stu-id="a44a7-124">If you're using your own data, the journal you choose must have **Check picking location** set to *No* and **Quarantine management** set to *No*.</span></span>
1. <span data-ttu-id="a44a7-125">Ustaw **Referencje** na *Zamowienie zakupu*.</span><span class="sxs-lookup"><span data-stu-id="a44a7-125">Set **Reference** to *Purchase order*.</span></span>
1. <span data-ttu-id="a44a7-126">Ustaw **Numer konta** na *1001*.</span><span class="sxs-lookup"><span data-stu-id="a44a7-126">Set **Account number** to *1001*.</span></span>
1. <span data-ttu-id="a44a7-127">Ustaw wartość **Numer** zamówienia zakupu wskazanego dla tego wykonania.</span><span class="sxs-lookup"><span data-stu-id="a44a7-127">Set **Number** to the number of the purchase order that you identified for this exercise.</span></span>

    <span data-ttu-id="a44a7-128">![Arkusz przyjęcia pozycji](../media/item-arrival-journal-header.png "Arkusz przyjęcia pozycji")</span><span class="sxs-lookup"><span data-stu-id="a44a7-128">![Item arrival journal](../media/item-arrival-journal-header.png "Item arrival journal")</span></span>

1. <span data-ttu-id="a44a7-129">Wybierz przycisk **OK**, aby utworzyć nagłówek arkusza.</span><span class="sxs-lookup"><span data-stu-id="a44a7-129">Select the **OK** to create the journal header.</span></span>
1. <span data-ttu-id="a44a7-130">W sekcji **Wiersze arkusza** wybierz opcję **Dodaj wiersz** i wprowadź następujące dane:</span><span class="sxs-lookup"><span data-stu-id="a44a7-130">In the **Journal lines** section, select **Add line** and enter the following data:</span></span>
    - <span data-ttu-id="a44a7-131">**Numer towaru** – Ustaw na *M9200*.</span><span class="sxs-lookup"><span data-stu-id="a44a7-131">**Item number** – Set to *M9200*.</span></span> <span data-ttu-id="a44a7-132">Ustawienia **lokalizacji,** **magazynu** i **ilości** zostaną ustawione na podstawie danych transakcji magazynowej dla 10 palet (1000 szt.).</span><span class="sxs-lookup"><span data-stu-id="a44a7-132">The **Site**, **Warehouse**, and **Quantity** will get set based on the inventory transaction data for the 10 pallets (1000 ea.).</span></span>
    - <span data-ttu-id="a44a7-133">**Lokalizacja** — ustawiono na *001*.</span><span class="sxs-lookup"><span data-stu-id="a44a7-133">**Location** – Set to  *001*.</span></span> <span data-ttu-id="a44a7-134">Ta lokalizacja nie śledzi numerów identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="a44a7-134">This specific location does not track license plates.</span></span>

    <span data-ttu-id="a44a7-135">![Wiersz arkusza rpzyjęcia towaru](../media/item-arrival-journal-line.png "Wiersz arkusza rpzyjęcia towaru")</span><span class="sxs-lookup"><span data-stu-id="a44a7-135">![Item arrival journal line](../media/item-arrival-journal-line.png "Item arrival journal line")</span></span>

    > [!NOTE]
    > <span data-ttu-id="a44a7-136">Pole **Data** określa dzień, kiedy dostępna ilość tego towaru zostanie zarejestrowana w magazynie.</span><span class="sxs-lookup"><span data-stu-id="a44a7-136">The **Date** field determines the date on which the on-hand quantity of this item will be registered in the inventory.</span></span>  
    >
    > <span data-ttu-id="a44a7-137">Pole **Identyfikator partii** zostanie wypełnione przez system, jeśli można je unikatowo zidentyfikować na podstawie dostarczonych informacji.</span><span class="sxs-lookup"><span data-stu-id="a44a7-137">The **Lot ID** will be populated by the system if it can be uniquely identified from the information provided.</span></span> <span data-ttu-id="a44a7-138">W przeciwnym razie należy go dodać ręcznie.</span><span class="sxs-lookup"><span data-stu-id="a44a7-138">Otherwise you will have to enter this manually.</span></span> <span data-ttu-id="a44a7-139">To pole jest wymagane i łączy tę rejestrację z określonym wierszem dokumentu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="a44a7-139">This is a required field, which links this registration to a specific source document line.</span></span>  

1. <span data-ttu-id="a44a7-140">W okienku akcji wybierz pozycję **Weryfikacja**.</span><span class="sxs-lookup"><span data-stu-id="a44a7-140">Select **Validate** on the Action Pane.</span></span> <span data-ttu-id="a44a7-141">Spowoduje to sprawdzenie, czy arkusz jest gotowy do zaksięgowania.</span><span class="sxs-lookup"><span data-stu-id="a44a7-141">This checks that the journal is ready to be posted.</span></span> <span data-ttu-id="a44a7-142">Jeżeli weryfikacja przyniesie wynik negatywny, trzeba naprawić błędy, zanim będzie można zaksięgować arkusz.</span><span class="sxs-lookup"><span data-stu-id="a44a7-142">If the validation fails you will need to fix the errors before you can post the journal.</span></span>  
1. <span data-ttu-id="a44a7-143">Zostanie otwarte okno dialogowe **Sprawdzanie arkusza**.</span><span class="sxs-lookup"><span data-stu-id="a44a7-143">The **Check journal** dialog box opens.</span></span> <span data-ttu-id="a44a7-144">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a44a7-144">Select **OK**.</span></span>
1. <span data-ttu-id="a44a7-145">Sprawdzanie Paska wiadomości.</span><span class="sxs-lookup"><span data-stu-id="a44a7-145">Review the message bar.</span></span> <span data-ttu-id="a44a7-146">Powinien tam być komunikat z informacją, że operacja została wykonana.</span><span class="sxs-lookup"><span data-stu-id="a44a7-146">There should be a message denoting that the operation was completed.</span></span>  
1. <span data-ttu-id="a44a7-147">W okienku akcji wybierz pozycję **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="a44a7-147">Select **Post** on the Action Pane.</span></span>
1. <span data-ttu-id="a44a7-148">Zostanie otwarte okno dialogowe **Księgowanie arkusza**.</span><span class="sxs-lookup"><span data-stu-id="a44a7-148">The **Post journal** dialog box opens.</span></span> <span data-ttu-id="a44a7-149">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a44a7-149">Select **OK**.</span></span>
1. <span data-ttu-id="a44a7-150">Sprawdzanie Paska wiadomości.</span><span class="sxs-lookup"><span data-stu-id="a44a7-150">Review the message bar.</span></span> <span data-ttu-id="a44a7-151">Powinien tam być komunikat z informacją, że operacja została wykonana.</span><span class="sxs-lookup"><span data-stu-id="a44a7-151">There should be messages denoting that the operation completed.</span></span>
1. <span data-ttu-id="a44a7-152">Wybierz opcje **Funkcje > Przyjęcie produktu** w okienku akcji, aby zaktualizować wiersz zamówienia zakupu i zakwitować przyjęcie produktów.</span><span class="sxs-lookup"><span data-stu-id="a44a7-152">Select **Functions > Product receipt** on the Action Pane to update the purchase order line and post a product receipt.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
