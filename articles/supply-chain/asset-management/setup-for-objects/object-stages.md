---
title: Stany cyklu życia składnika majątku
description: W tym temacie wyjaśniono stany cyklu życia składników majątku i modele cyklu życia w zarządzaniu składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetLifecycleModelStateNext, EntAssetObjectLifecycleState, EntAssetLifecycleStateUpdate, EntAssetObjectLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 566036c6361194d910a0fc34bd5d72147585ec4f
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889920"
---
# <a name="asset-lifecycle-states"></a><span data-ttu-id="b203f-103">Stany cyklu życia składnika majątku</span><span class="sxs-lookup"><span data-stu-id="b203f-103">Asset lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="b203f-104">W tym temacie wyjaśniono stany cyklu życia składników majątku i modele cyklu życia w zarządzaniu składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="b203f-104">This topic explains asset lifecycle states and lifecycle models in Asset Management.</span></span> <span data-ttu-id="b203f-105">Stany cyklu życia składnika majątku są używane do definiowania, czy składnik majątku jest aktywny czy nieaktywny.</span><span class="sxs-lookup"><span data-stu-id="b203f-105">Asset lifecycle states are used to define whether an asset is active or inactive.</span></span> <span data-ttu-id="b203f-106">Można na przykład skonfigurować stany cyklu życia składnika majątku, takie jak **Utworzone**, **Aktywne**i **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="b203f-106">For example, you can set up asset lifecycle states such as **Created**, **Active**, and **Terminated**.</span></span>

> [!NOTE]
> - <span data-ttu-id="b203f-107">Stany cyklu życia żądania są połączone ze stanami cyklu życia składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="b203f-107">Request lifecycle states are linked to asset lifecycle states.</span></span> <span data-ttu-id="b203f-108">Dlatego kiedy żądanie zostanie zmienione na nowy stan cyklu życia żądania, składnik majątku, dołączony do żądania jest zmieniany na nowy stan cyklu życia składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="b203f-108">Therefore, when a request is changed to a new request lifecycle state, the asset that is attached to the request is changed to a new asset lifecycle state.</span></span> <span data-ttu-id="b203f-109">Na przykład, jeśli stan cyklu życia żądania zostanie zmieniony na **Przychodzący**, stan cyklu życia dołączonego składnika majątku zostanie zmieniony na stan cyklu życia wybranego w polu **stan cyklu życia przychodzącego** na skróconej karcie **Stan cyklu życia składnika majątku** na stronie **Modele stanu cyklu życia składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="b203f-109">For example, if the lifecycle state of a request is changed to **Inbound**, the lifecycle state of the attached asset is changed to the lifecycle state that is selected in the **Inbound lifecycle state** field on the **Asset lifecycle state** FastTab of the **Asset lifecycle state models** page.</span></span> 


<span data-ttu-id="b203f-110">Stany cyklu życia składnika majątku można skonfigurować w modelach cyklu życia składnika majątku, w których można zdefiniować wymagane stany cyklu życia dla różnych typów składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="b203f-110">Asset lifecycle states can be set up in asset lifecycle models, where you can define the required lifecycle states for various types of assets.</span></span> <span data-ttu-id="b203f-111">Najpierw konfiguruje się stany cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="b203f-111">You first set up lifecycle states.</span></span> <span data-ttu-id="b203f-112">Następnie należy utworzyć model cyklu życia i wybrać niego stan cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="b203f-112">You then create a lifecycle model and select lifecycle states for it.</span></span>

1. <span data-ttu-id="b203f-113">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Składniki majątku** \> **Stany cyklu życia**.</span><span class="sxs-lookup"><span data-stu-id="b203f-113">Select **Asset management** \> **Setup** \> **Assets** \> **Lifecycle states**.</span></span>
2. <span data-ttu-id="b203f-114">Wybierz pozycję **Nowy**, aby utworzyć nowy stan cyklu życia składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="b203f-114">Select **New** to create a new asset lifecycle state.</span></span>
3. <span data-ttu-id="b203f-115">W polu **Stan cyklu życia** wprowadź identyfikator stanu cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="b203f-115">In the **Lifecycle state** field, enter the lifecycle state ID.</span></span>
4. <span data-ttu-id="b203f-116">W polu **Nazwa** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="b203f-116">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="b203f-117">Pole **Modele cyklu życia** pokazuje liczbę modeli cyklu życia składnika majątku, które używają stanu cyklu życia składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="b203f-117">The **Lifecycle models** field shows the number of asset lifecycle models that use the asset lifecycle state.</span></span>

5. <span data-ttu-id="b203f-118">Ustaw opcję **Aktywny** na **Tak**, jeśli stan cyklu życia powinien być aktywnym stanem cyklu życia (innymi słowy, jeśli zlecenia pracy mogą być tworzone dla składników majątku, które są w tym stanie cyklu życia).</span><span class="sxs-lookup"><span data-stu-id="b203f-118">Set the **Active** option to **Yes** if this lifecycle state should be an active lifecycle state (in other words, if work orders can be created for assets that are in this lifecycle state).</span></span>
6. <span data-ttu-id="b203f-119">Ustaw opcję **Usuń otwarte wiersze kalendarza** na **Tak**, jeśli otwarte wiersze kalendarza składnika majątku, które mają stan cyklu życia składnika majątku **Utworzony**, powinny zostać usunięte, gdy są w tym stanie cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="b203f-119">Set the **Delete open calendar lines** option to **Yes** if open asset calendar lines that have an asset lifecycle state of **Created** should be deleted when they are in this lifecycle state.</span></span> <span data-ttu-id="b203f-120">To ustawienie jest przydatne, jeśli chcesz wyczyścić wszystkie otwarte harmonogramy konserwacji, które nie są już istotne dla składnika majątku (na przykład, jeśli składnik majątku nie jest już aktywny).</span><span class="sxs-lookup"><span data-stu-id="b203f-120">This setting is useful if you want to clean up any open maintenance schedules that are no longer relevant for the asset (for example, if the asset is no longer active).</span></span>

> [!NOTE]
> <span data-ttu-id="b203f-121">Stany cyklu życia składnika majątku, modele cyklu życia składnika majątku i typy składnika majątku są powiązane.</span><span class="sxs-lookup"><span data-stu-id="b203f-121">Asset lifecycle states, asset lifecycle models, and asset types are related.</span></span> <span data-ttu-id="b203f-122">Są one używane w taki sam sposób jak stany cyklu życia zlecenia pracy, modele cyklu życia zlecenia pracy i typy zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="b203f-122">They are used in the same way as work order lifecycle states, work order lifecycle models, and work order types.</span></span> 


<span data-ttu-id="b203f-123">Po utworzeniu stanów cyklu życia wymaganego składnika majątku można skonfigurować stany cyklu życia w modelach cyklu życia składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="b203f-123">After you've created the required asset lifecycle states, you can set up lifecycle states in asset lifecycle models.</span></span>

1. <span data-ttu-id="b203f-124">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Składniki majątku** \> **Modele cyklu życia**.</span><span class="sxs-lookup"><span data-stu-id="b203f-124">Select **Asset management** \> **Setup** \> **assets** \> **lifecycle models**.</span></span>
2. <span data-ttu-id="b203f-125">Wybierz pozycję **Nowy**, aby utworzyć nowy model cyklu życia składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="b203f-125">Select **New** to create a new asset lifecycle model.</span></span>
3. <span data-ttu-id="b203f-126">W polu **Model cyklu życia** wprowadź identyfikator modelu cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="b203f-126">In the **Lifecycle model** field, enter the lifecycle model ID.</span></span>
4. <span data-ttu-id="b203f-127">W polu **Nazwa** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="b203f-127">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="b203f-128">Pole **Stany cyklu życia** pokazuje liczbę stanów cyklu życia składnika majątku, które są wybrane w modelu cyklu życia składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="b203f-128">The **Lifecycle states** field shows the number of asset lifecycle states that are selected in the asset lifecycle model.</span></span> <span data-ttu-id="b203f-129">Pole **Typy składników majątku** zawiera liczbę typów składników majątku, które są używane w modelu cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="b203f-129">The **Asset types** field shows the number of asset types that use the lifecycle model.</span></span>

5. <span data-ttu-id="b203f-130">Na skróconej karcie **Stany cyklu życia** wybierz stany cyklu życia składnika majątku, które powinny być uwzględnione w modelu cyklu życia składnika majątku:</span><span class="sxs-lookup"><span data-stu-id="b203f-130">On the **Lifecycle states** FastTab, select the asset lifecycle states that should be included in the asset lifecycle model:</span></span>

    - <span data-ttu-id="b203f-131">Aby użyć stanu cyklu życia dla modelu, zaznacz go w sekcji **Pozostałe stany cyklu życia**, a następnie wybierz przycisk strzałki w prawo ![Strzałka w prawo](media/15-setup-for-objects.png), aby przenieść go do sekcji **Wybrane stany cyklu życia**.</span><span class="sxs-lookup"><span data-stu-id="b203f-131">To use a lifecycle state for the model, select it in the **Lifecycle states remaining** section, and then select the right arrow button ![Right arrow](media/15-setup-for-objects.png) to move it to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="b203f-132">Aby użyć wszystkich dostępnych stanów cyklu życia dla modelu, wybierz przycisk **Wszystkie dostępne stany cyklu życia** ![Wszystkie dostępne stany cyklu życia](media/20-setup-for-objects.png).</span><span class="sxs-lookup"><span data-stu-id="b203f-132">To use all the available lifecycle states for the model, select the **All available lifecycle states** button ![All available lifecycle states](media/20-setup-for-objects.png).</span></span> <span data-ttu-id="b203f-133">Wszystkie stany cyklu życia są przenoszone do sekcji **Wybrane cykle życia**.</span><span class="sxs-lookup"><span data-stu-id="b203f-133">All lifecycle states are transferred to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="b203f-134">Aby usunąć stan cyklu życia z modelu, wybierz go w sekcji **wybrane stany cyklu życia**, a następnie wybierz przycisk strzałki lewo ![Strzałka w lewo](media/16-setup-for-objects.png), aby przenieść go do sekcji **Pozostałe stany cyklu życia**.</span><span class="sxs-lookup"><span data-stu-id="b203f-134">To remove a lifecycle state from the model, select it in the **lifecycle states selected** section, and then select the left arrow button ![Left arrow](media/16-setup-for-objects.png) to move it to the **Lifecycle states remaining** section.</span></span>

6. <span data-ttu-id="b203f-135">Wybierz pozycję **Aktualizacje stanu cyklu życia**, aby określić stany cyklu życia składnika majątku, które mogą być wybranym stanem cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="b203f-135">Select **Lifecycle state updates** to define the asset lifecycle states that can follow a selected lifecycle state.</span></span>
7. <span data-ttu-id="b203f-136">Możesz użyć skróconej karty **Stan składnika majątku**, jeśli obsługujesz składniki majątku otrzymywane do naprawy.</span><span class="sxs-lookup"><span data-stu-id="b203f-136">You use the **Asset state** FastTab if you handle assets that you receive for repair.</span></span> <span data-ttu-id="b203f-137">W sekcji **Przychodzące/wychodzące** można wybrać stany cyklu życia składnika majątku, aby wskazać przepływ pracy dla składnika majątku otrzymywanego w celu naprawy.</span><span class="sxs-lookup"><span data-stu-id="b203f-137">In the **Inbound/outbound** section, you can select asset lifecycle states to indicate the workflow of an asset that you receive for repair.</span></span> <span data-ttu-id="b203f-138">Jeśli użyczasz składników majątku klientom lub oddziałom, w sekcji **Użyczenie** wybierz stany cyklu życia użyczonych składników majątku.</span><span class="sxs-lookup"><span data-stu-id="b203f-138">If you offer loan assets to customers or departments, in the **Loan** section, you can select lifecycle states for loan assets.</span></span>
