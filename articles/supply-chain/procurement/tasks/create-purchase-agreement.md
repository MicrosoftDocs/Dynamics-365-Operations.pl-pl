---
title: Tworzenie umowy zakupu
description: Ten temat przeprowadzi Cię przez proces tworzenia umowy zakupu.
author: mkirknel
manager: tfehr
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1edfd4e56910376d0596eec5eff2af888f7dc98d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207745"
---
# <a name="create-a-purchase-agreement"></a><span data-ttu-id="08aeb-103">Tworzenie umowy zakupu</span><span class="sxs-lookup"><span data-stu-id="08aeb-103">Create a purchase agreement</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="08aeb-104">Ten temat przeprowadzi Cię przez proces tworzenia umowy zakupu.</span><span class="sxs-lookup"><span data-stu-id="08aeb-104">This topic guides you through the creation of a purchase agreement.</span></span> <span data-ttu-id="08aeb-105">Zazwyczaj robi to kierownik ds. zakupów.</span><span class="sxs-lookup"><span data-stu-id="08aeb-105">This would typically be done by a purchasing manager.</span></span> <span data-ttu-id="08aeb-106">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="08aeb-106">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="08aeb-107">Przed rozpoczęciem trzeba mieć skonfigurowaną klasyfikacji umów zakupu.</span><span class="sxs-lookup"><span data-stu-id="08aeb-107">You need to have set up purchase agreement classifications before you start.</span></span> <span data-ttu-id="08aeb-108">Po utworzeniu umowy można jej używać podczas tworzenia zamówienia zakupu. Spowoduje to skopiowanie warunków umowy do nagłówka oraz do wszystkich wierszy w zamówieniu, których dotyczy umowa.</span><span class="sxs-lookup"><span data-stu-id="08aeb-108">Once you've created an agreement you can use it when you create a PO, and this will copy the purchase agreement conditions to the header and to any lines in the order that are affected by the agreement.</span></span>


## <a name="create-a-new-purchase-agreement"></a><span data-ttu-id="08aeb-109">Tworzenie nowej umowy zakupu</span><span class="sxs-lookup"><span data-stu-id="08aeb-109">Create a new purchase agreement</span></span>
1. <span data-ttu-id="08aeb-110">Wybierz kolejno **Okienko nawigacji> Moduły > Zaopatrzenie i sourcing > Umowy zakupu > Umowy zakupu**.</span><span class="sxs-lookup"><span data-stu-id="08aeb-110">Go to **Navigation pane > Modules > Procurement and sourcing > Purchase agreements > Purchase agreements**.</span></span>
2. <span data-ttu-id="08aeb-111">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="08aeb-111">Click **New**.</span></span>
3. <span data-ttu-id="08aeb-112">W polu **Konto dostawcy** wybierz wiersz z żądanym rekordem z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="08aeb-112">In the **Vendor account** field, select the drop-down menu and select the row of the desired record.</span></span>
4. <span data-ttu-id="08aeb-113">W polu **Klasyfikacja umowy zakupu** wybierz wiersz z żądanym rekordem z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="08aeb-113">In the **Purchase agreement classification** field, select the drop-down menu and select the row of the desired record.</span></span>
5. <span data-ttu-id="08aeb-114">Rozwiń skróconą kartę **Ogólne**.</span><span class="sxs-lookup"><span data-stu-id="08aeb-114">Expand the **General** FastTab.</span></span>
6. <span data-ttu-id="08aeb-115">W polu **Data wygaśnięcia** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="08aeb-115">In the **Expiration date** field, enter a date.</span></span>

    - <span data-ttu-id="08aeb-116">Ta data ważności będzie domyślna dla wszystkich wierszy zobowiązań i określi, jak długo każde konkretne zobowiązanie jest ważne.</span><span class="sxs-lookup"><span data-stu-id="08aeb-116">This expiration date will be the default for all commitment lines and will determine how long each specific commitment is valid.</span></span>  

7. <span data-ttu-id="08aeb-117">W polu **Tytuł dokumentu** nadaj nazwę umowie zakupu.</span><span class="sxs-lookup"><span data-stu-id="08aeb-117">In the **Document title** field, type a name for your purchase agreement.</span></span>

    - <span data-ttu-id="08aeb-118">Pozostaw w polu **Domyślne zobowiązanie** wartość **Zobowiązanie co do ilości produktu** (lub ją zmień na tą, jeśli jest ustawiona inna).</span><span class="sxs-lookup"><span data-stu-id="08aeb-118">Leave the **Default commitment** field set to **Product quantity commitment** (or change it if it's not set to this).</span></span>  
    - <span data-ttu-id="08aeb-119">Domyślna wartość zobowiązania określa opcje dostępne w wierszach umowy.</span><span class="sxs-lookup"><span data-stu-id="08aeb-119">The default commitment value determines your options on the agreement lines.</span></span> <span data-ttu-id="08aeb-120">Jeśli przy tworzeniu wierszy umowy potrzebujesz nowego typu zobowiązania, należy zmienić domyślne zobowiązanie w nagłówku.</span><span class="sxs-lookup"><span data-stu-id="08aeb-120">If you need a new commitment type when you're creating the agreement lines, you need to change the default commitment on the header.</span></span> <span data-ttu-id="08aeb-121">Istnieją 4 rodzaje zobowiązań: **Zobowiązanie co do ilości produktu** — na określoną ilość produktu; **Zobowiązanie co do wartości produktu** — na określoną wartość produktu w walucie; **Zobowiązanie co do wartości w ramach kategorii produktu** — na wartość produktu w określonej walucie w kategorii zaopatrzenia, gdzie kwota może dotyczyć towaru z katalogu lub spoza katalogu; **Zobowiązanie co do wartości** — na określoną kwocie w walucie, która może być pokryta przez jakikolwiek produkt z dowolnej kategorii zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="08aeb-121">There are 4 types of commitments: **Product quantity commitment** - for a specific quantity of a product; **Product value commitment** - for a specific currency amount of a product; **Product category value commitment** - for a specific currency amount in a procurement category where the amount can be for a catalog item or a non-catalog item; **Value commitment** - for a specific currency amount which can be fulfilled by any product or by any procurement category.</span></span>  

8. <span data-ttu-id="08aeb-122">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="08aeb-122">Select **OK**.</span></span>

## <a name="add-a-commitment"></a><span data-ttu-id="08aeb-123">Dodawanie zobowiązania</span><span class="sxs-lookup"><span data-stu-id="08aeb-123">Add a commitment</span></span>
1. <span data-ttu-id="08aeb-124">Wybierz **Dodaj wiersz**.</span><span class="sxs-lookup"><span data-stu-id="08aeb-124">Select **Add line**.</span></span>
2. <span data-ttu-id="08aeb-125">W polu **Numer produktu** wybierz odpowiedni rekord z menu listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="08aeb-125">In the **Item number** field, select the desired record from the drop-down menu.</span></span>
3. <span data-ttu-id="08aeb-126">W polu **Ilość** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="08aeb-126">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="08aeb-127">Jest to ilość całkowita, jaką zgodzono się kupić od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="08aeb-127">This is the total quantity that you have agreed to buy from your vendor.</span></span>  
4. <span data-ttu-id="08aeb-128">W polu **Cena jednostkowa** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="08aeb-128">In the **Unit price** field, enter a number.</span></span>
5. <span data-ttu-id="08aeb-129">Rozwiń sekcję **Szczegóły wiersza**.</span><span class="sxs-lookup"><span data-stu-id="08aeb-129">Expand the **Line details** section.</span></span>
6. <span data-ttu-id="08aeb-130">W opcji **Wymuszono maks**. zaznacz wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="08aeb-130">Set the **Max is enforced** option to **Yes**.</span></span> <span data-ttu-id="08aeb-131">Opcja **Wymuszono maks.** ogranicza użycie zobowiązania.</span><span class="sxs-lookup"><span data-stu-id="08aeb-131">The **Max is enforced** option limits the use of the commitment.</span></span> <span data-ttu-id="08aeb-132">Można kupować tylko do ilości określonej w polu **Ilość** dla wiersza.</span><span class="sxs-lookup"><span data-stu-id="08aeb-132">You can only purchase up to the quantity that's specified in the **Quantity** field for the line.</span></span>  

## <a name="add-header-conditions"></a><span data-ttu-id="08aeb-133">Dodawanie warunków nagłówka</span><span class="sxs-lookup"><span data-stu-id="08aeb-133">Add header conditions</span></span>
1. <span data-ttu-id="08aeb-134">W okienku akcji kliknij pozycję **Opcje**.</span><span class="sxs-lookup"><span data-stu-id="08aeb-134">On the Action Pane, select **Options**.</span></span>
2. <span data-ttu-id="08aeb-135">Wybierz **Zmień widok**.</span><span class="sxs-lookup"><span data-stu-id="08aeb-135">Select **Change view**.</span></span>
3. <span data-ttu-id="08aeb-136">Wybierz **Widok nagłówka**.</span><span class="sxs-lookup"><span data-stu-id="08aeb-136">Select **Header view**.</span></span>
4. <span data-ttu-id="08aeb-137">Rozwiń sekcję **Warunki**.</span><span class="sxs-lookup"><span data-stu-id="08aeb-137">Expand the **Terms** section.</span></span>
5. <span data-ttu-id="08aeb-138">W polu **Metoda płatności** wybierz odpowiedni rekord z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="08aeb-138">In the **Method of payment** field, select the desired record in the drop-down menu.</span></span> <span data-ttu-id="08aeb-139">W tym miejscu są domyślnie wyświetlane warunki płatności z konta dostawcy.</span><span class="sxs-lookup"><span data-stu-id="08aeb-139">The payment terms from the vendor account are shown here by default.</span></span>  
6. <span data-ttu-id="08aeb-140">W polu **Metoda dostawy** wybierz odpowiedni rekord z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="08aeb-140">In the **Mode of delivery** field, select the desired record in the drop-down menu.</span></span>
7. <span data-ttu-id="08aeb-141">W polu **Warunki dostawy** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="08aeb-141">In the **Delivery terms** field, select the drop-down button to open the lookup.</span></span>

## <a name="confirm-and-activate-the-agreement"></a><span data-ttu-id="08aeb-142">Potwierdzanie i aktywacja umowy</span><span class="sxs-lookup"><span data-stu-id="08aeb-142">Confirm and activate the agreement</span></span>
1. <span data-ttu-id="08aeb-143">W okienku akcji kliknij pozycję **Umowa zakupu**.</span><span class="sxs-lookup"><span data-stu-id="08aeb-143">On the Action Pane, select **Purchase agreement**.</span></span>
2. <span data-ttu-id="08aeb-144">Wybierz **Potwierdzenie**.</span><span class="sxs-lookup"><span data-stu-id="08aeb-144">Select **Confirmation**.</span></span> <span data-ttu-id="08aeb-145">W opcji **Oznaczenie umowy jako obowiązującej** zaznacz wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="08aeb-145">Set the **Mark agreement as effective** option to **Yes**.</span></span>  
3. <span data-ttu-id="08aeb-146">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="08aeb-146">Select **OK**.</span></span>
4. <span data-ttu-id="08aeb-147">W okienku akcji kliknij pozycję **Umowa zakupu**.</span><span class="sxs-lookup"><span data-stu-id="08aeb-147">On the Action Pane, select **Purchase agreement**.</span></span>
5. <span data-ttu-id="08aeb-148">Wybierz **Potwierdzenia umowy zakupu**.</span><span class="sxs-lookup"><span data-stu-id="08aeb-148">Select **Purchase agreement confirmations**.</span></span> <span data-ttu-id="08aeb-149">Opcja **Podgląd/drukuj** umożliwia wygenerowanie dokumentu umowy zakupu, który następnie można wydrukować lub wysłać do dostawcy.</span><span class="sxs-lookup"><span data-stu-id="08aeb-149">The **Preview/Print** option allows you to generate a document for the purchase agreement which you can then print or send to the vendor.</span></span> <span data-ttu-id="08aeb-150">Jeśli później zaktualizujesz umowę i ponownie ją potwierdzisz, obie wersje będą wyświetlane w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="08aeb-150">If you update the agreement later on and re-confirm it, both versions will be shown here.</span></span>  
6. <span data-ttu-id="08aeb-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="08aeb-151">Close the page.</span></span>

