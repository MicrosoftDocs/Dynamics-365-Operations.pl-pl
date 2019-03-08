---
title: Tworzenie umowy zakupu
description: Ta procedura przeprowadzi Cię przez proces tworzenia umowy zakupu.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b317f0a0fc8f198bad9501f325557ac2a4796989
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "338620"
---
# <a name="create-a-purchase-agreement"></a><span data-ttu-id="84a2b-103">Tworzenie umowy zakupu</span><span class="sxs-lookup"><span data-stu-id="84a2b-103">Create a purchase agreement</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="84a2b-104">Ta procedura przeprowadzi Cię przez proces tworzenia umowy zakupu.</span><span class="sxs-lookup"><span data-stu-id="84a2b-104">This procedure guides you through the creation of a purchase agreement.</span></span> <span data-ttu-id="84a2b-105">Zazwyczaj robi to kierownik ds. zakupów.</span><span class="sxs-lookup"><span data-stu-id="84a2b-105">This would typically be done by a purchasing manager.</span></span> <span data-ttu-id="84a2b-106">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="84a2b-106">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="84a2b-107">Przed rozpoczęciem trzeba mieć skonfigurowaną klasyfikacji umów zakupu.</span><span class="sxs-lookup"><span data-stu-id="84a2b-107">You need to have set up purchase agreement classifications before you start.</span></span> <span data-ttu-id="84a2b-108">Po utworzeniu umowy można jej używać podczas tworzenia zamówienia zakupu. Spowoduje to skopiowanie warunków umowy do nagłówka oraz do wszystkich wierszy w zamówieniu, których dotyczy umowa.</span><span class="sxs-lookup"><span data-stu-id="84a2b-108">Once you've created an agreement you can use it when you create a PO, and this will copy the purchase agreement conditions to the header and to any lines in the order that are affected by the agreement.</span></span>


## <a name="create-a-new-purchase-agreement"></a><span data-ttu-id="84a2b-109">Tworzenie nowej umowy zakupu</span><span class="sxs-lookup"><span data-stu-id="84a2b-109">Create a new purchase agreement</span></span>
1. <span data-ttu-id="84a2b-110">Wybierz kolejno opcje Zaopatrzenie i sourcing > Umowy zakupu > Umowy zakupu.</span><span class="sxs-lookup"><span data-stu-id="84a2b-110">Go to Procurement and sourcing > Purchase agreements > Purchase agreements.</span></span>
2. <span data-ttu-id="84a2b-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="84a2b-111">Click New.</span></span>
3. <span data-ttu-id="84a2b-112">W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="84a2b-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="84a2b-113">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="84a2b-113">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="84a2b-114">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="84a2b-114">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="84a2b-115">W polu Klasyfikacja umowy zakupu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="84a2b-115">In the Purchase agreement classification field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="84a2b-116">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="84a2b-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="84a2b-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="84a2b-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="84a2b-118">Rozwiń sekcję Ogólne.</span><span class="sxs-lookup"><span data-stu-id="84a2b-118">Expand the General section.</span></span>
10. <span data-ttu-id="84a2b-119">W polu Data wygaśnięcia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="84a2b-119">In the Expiration date field, enter a date.</span></span>
    * <span data-ttu-id="84a2b-120">Ta data ważności będzie domyślna dla wszystkich wierszy zobowiązań i określi, jak długo każde konkretne zobowiązanie jest ważne.</span><span class="sxs-lookup"><span data-stu-id="84a2b-120">This expiration date will be the default for all commitment lines and will determine how long each specific commitment is valid.</span></span>  
11. <span data-ttu-id="84a2b-121">W polu Tytuł dokumentu nadaj nazwę umowie zakupu.</span><span class="sxs-lookup"><span data-stu-id="84a2b-121">In the Document title field, type a name for your purchase agreement.</span></span>
    * <span data-ttu-id="84a2b-122">Pozostaw w polu Domyślne zobowiązanie wartość Zobowiązanie co do ilości produktu (lub ją zmień na tą, jeśli jest ustawiona inna).</span><span class="sxs-lookup"><span data-stu-id="84a2b-122">Leave the Default commitment field set to Product quantity commitment (or change it if it’s not set to this).</span></span>  
    * <span data-ttu-id="84a2b-123">Domyślna wartość zobowiązania określa opcje dostępne w wierszach umowy.</span><span class="sxs-lookup"><span data-stu-id="84a2b-123">The default commitment value determines your options on the agreement lines.</span></span> <span data-ttu-id="84a2b-124">Jeśli przy tworzeniu wierszy umowy potrzebujesz nowego typu zobowiązania, należy zmienić domyślne zobowiązanie w nagłówku.</span><span class="sxs-lookup"><span data-stu-id="84a2b-124">If you need a new commitment type when you’re creating the agreement lines, you need to change the default commitment on the header.</span></span>  <span data-ttu-id="84a2b-125">Istnieją 4 rodzaje zobowiązań: Zobowiązanie co do ilości produktu — na określoną ilość produktu; Zobowiązanie co do wartości produktu — na określoną wartość produktu w walucie; Zobowiązanie co do wartości w ramach kategorii produktu — na wartość produktu w określonej walucie w kategorii zaopatrzenia, gdzie kwota może dotyczyć towaru z katalogu lub spoza katalogu; Zobowiązanie co do wartości — na określoną kwocie w walucie, która może być pokryta przez jakikolwiek produkt z dowolnej kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="84a2b-125">There are 4 types of commitments: Product quantity commitment - for a specific quantity of a product; Product value commitment - for a specific currency amount of a product; Product category value commitment - for a specific currency amount in a procurement category where the amount can be for a catalog item or a non-catalog item; Value commitment - for a specific currency amount which can be fulfilled by any product or by any procurement category.</span></span>  
12. <span data-ttu-id="84a2b-126">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="84a2b-126">Click OK.</span></span>

## <a name="add-a-commitment"></a><span data-ttu-id="84a2b-127">Dodawanie zobowiązania</span><span class="sxs-lookup"><span data-stu-id="84a2b-127">Add a commitment</span></span>
1. <span data-ttu-id="84a2b-128">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="84a2b-128">Click Add line.</span></span>
2. <span data-ttu-id="84a2b-129">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="84a2b-129">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="84a2b-130">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="84a2b-130">In the Item number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="84a2b-131">Wybierz produkt, dla którego chcesz dodać zobowiązanie.</span><span class="sxs-lookup"><span data-stu-id="84a2b-131">Select the product you want to add a commitment for.</span></span>
5. <span data-ttu-id="84a2b-132">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="84a2b-132">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="84a2b-133">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="84a2b-133">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="84a2b-134">Jest to ilość całkowita, jaką zgodzono się kupić od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="84a2b-134">This is the total quantity that you have agreed to buy from your vendor.</span></span>  
7. <span data-ttu-id="84a2b-135">Wprowadź liczbę w polu Cena jednostkowa.</span><span class="sxs-lookup"><span data-stu-id="84a2b-135">In the Unit price field, enter a number.</span></span>
8. <span data-ttu-id="84a2b-136">Rozwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="84a2b-136">Expand the Line details section.</span></span>
9. <span data-ttu-id="84a2b-137">W opcji Wymuszono maks. zaznacz wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="84a2b-137">Set the Max is enforced option to Yes.</span></span>
    * <span data-ttu-id="84a2b-138">Opcja Wymuszono maks. ogranicza użycie zobowiązania.</span><span class="sxs-lookup"><span data-stu-id="84a2b-138">The Max is enforced option limits the use of the commitment.</span></span> <span data-ttu-id="84a2b-139">Można kupować tylko do ilości określonej w polu Ilość dla wiersza.</span><span class="sxs-lookup"><span data-stu-id="84a2b-139">You can only purchase up to the quantity that's specified in the Quantity field for the line.</span></span>  
10. <span data-ttu-id="84a2b-140">Zwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="84a2b-140">Collapse the Line details section.</span></span>

## <a name="add-header-conditions"></a><span data-ttu-id="84a2b-141">Dodawanie warunków nagłówka</span><span class="sxs-lookup"><span data-stu-id="84a2b-141">Add header conditions</span></span>
1. <span data-ttu-id="84a2b-142">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="84a2b-142">On the Action Pane, click Options.</span></span>
2. <span data-ttu-id="84a2b-143">Kliknij przycisk Zmień widok.</span><span class="sxs-lookup"><span data-stu-id="84a2b-143">Click Change view.</span></span>
3. <span data-ttu-id="84a2b-144">Kliknij opcję Widok nagłówka.</span><span class="sxs-lookup"><span data-stu-id="84a2b-144">Click Header view.</span></span>
4. <span data-ttu-id="84a2b-145">Rozwiń sekcję Warunki.</span><span class="sxs-lookup"><span data-stu-id="84a2b-145">Expand the Terms section.</span></span>
5. <span data-ttu-id="84a2b-146">W polu Metoda płatności kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="84a2b-146">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="84a2b-147">W tym miejscu są domyślnie wyświetlane warunki płatności z konta dostawcy.</span><span class="sxs-lookup"><span data-stu-id="84a2b-147">The payment terms from the vendor account are shown here by default.</span></span>       
6. <span data-ttu-id="84a2b-148">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="84a2b-148">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="84a2b-149">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="84a2b-149">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="84a2b-150">W polu Metoda dostawy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="84a2b-150">In the Mode of delivery field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="84a2b-151">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="84a2b-151">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="84a2b-152">W polu Warunki dostawy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="84a2b-152">In the Delivery terms field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="84a2b-153">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="84a2b-153">In the list, click the link in the selected row.</span></span>

## <a name="confirm-and-activate-the-agreement"></a><span data-ttu-id="84a2b-154">Potwierdzanie i aktywacja umowy</span><span class="sxs-lookup"><span data-stu-id="84a2b-154">Confirm and activate the agreement</span></span>
1. <span data-ttu-id="84a2b-155">W okienku akcji kliknij pozycję Umowa zakupu.</span><span class="sxs-lookup"><span data-stu-id="84a2b-155">On the Action Pane, click Purchase agreement.</span></span>
2. <span data-ttu-id="84a2b-156">Kliknij opcję Potwierdzenie.</span><span class="sxs-lookup"><span data-stu-id="84a2b-156">Click Confirmation.</span></span>
    * <span data-ttu-id="84a2b-157">W opcji Oznaczenie umowy jako obowiązującej zaznacz wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="84a2b-157">Set the Mark agreement as effective option to Yes.</span></span>  
3. <span data-ttu-id="84a2b-158">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="84a2b-158">Click OK.</span></span>
4. <span data-ttu-id="84a2b-159">W okienku akcji kliknij pozycję Umowa zakupu.</span><span class="sxs-lookup"><span data-stu-id="84a2b-159">On the Action Pane, click Purchase agreement.</span></span>
5. <span data-ttu-id="84a2b-160">Kliknij opcję Potwierdzenia umowy zakupu.</span><span class="sxs-lookup"><span data-stu-id="84a2b-160">Click Purchase agreement confirmations.</span></span>
    * <span data-ttu-id="84a2b-161">Opcja Podgląd/drukuj umożliwia wygenerowanie dokumentu umowy zakupu, który następnie można wydrukować lub wysłać do dostawcy.</span><span class="sxs-lookup"><span data-stu-id="84a2b-161">The Preview/Print option allows you to generate a document for the purchase agreement which you can then print or send to the vendor.</span></span> <span data-ttu-id="84a2b-162">Jeśli później zaktualizujesz umowę i ponownie ją potwierdzisz, obie wersje będą wyświetlane w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="84a2b-162">If you update the agreement later on and re-confirm it, both versions will be shown here.</span></span>  
6. <span data-ttu-id="84a2b-163">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="84a2b-163">Close the page.</span></span>

