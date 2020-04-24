---
title: Ocena warunku
description: W tym temacie wyjaśniono, jak utworzyć szablon oceny warunku i jak zarejestrować składnik majątku w Zarządzaniu składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e2694b3ee51e2619a94e7ea2f4039fb52adddbbc
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208922"
---
# <a name="condition-assessment"></a><span data-ttu-id="36baf-103">Ocena warunku</span><span class="sxs-lookup"><span data-stu-id="36baf-103">Condition assessment</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="36baf-104">W tym temacie wyjaśniono, jak utworzyć szablon oceny warunku i jak zarejestrować składnik majątku w Zarządzaniu składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="36baf-104">This topic explains how to create a condition assessment template and registration on an asset in Asset Management.</span></span> <span data-ttu-id="36baf-105">Ocena stanu jest wykonywana w regularnych odstępach czasu, a podstawowym celem jest tworzenie i utrzymywanie danych o stanie składników majątku.</span><span class="sxs-lookup"><span data-stu-id="36baf-105">Condition assessment is performed at regular intervals, and the primary objective is to create and maintain condition data on assets.</span></span> <span data-ttu-id="36baf-106">Z punktu widzenia konserwacji zapobiegawczej ważne jest monitorowanie kluczowych informacji, takich jak aktualny stan i pozostały okres eksploatacji.</span><span class="sxs-lookup"><span data-stu-id="36baf-106">Seen from a preventive maintenance perspective, it is important to monitor key information such as current condition, and remaining life span.</span></span> <span data-ttu-id="36baf-107">Ponadto, jeśli przeprowadzą Państwo ocenę stanu w regularnych odstępach czasu, będą Państwo mogli monitorować i porównywać warunki na maszynie w fabryce.</span><span class="sxs-lookup"><span data-stu-id="36baf-107">Furthermore, if you carry out condition assessment at regular intervals, you will be able to monitor and compare conditions on the machinery in your factory.</span></span>

<span data-ttu-id="36baf-108">Ocena stanu może być wykorzystana do pomiaru i monitorowania wielu warunków na sprzęcie.</span><span class="sxs-lookup"><span data-stu-id="36baf-108">Condition assessment can be used to measure and monitor many conditions on your equipment.</span></span> <span data-ttu-id="36baf-109">Przykład: można zmierzyć drgania maszyny.</span><span class="sxs-lookup"><span data-stu-id="36baf-109">Example: You could measure vibrations on your machinery.</span></span> <span data-ttu-id="36baf-110">Po zarejestrowaniu pomiarów drgań w zarządzaniu składnikami majątku, na różnego rodzaju sprzęcie można wyszukać najnowszą zarejestrowaną ocenę i wyświetlić pomiary drgań.</span><span class="sxs-lookup"><span data-stu-id="36baf-110">After you have registered vibration measurements in Asset Management on various types of equipment, you can search for the latest registered assessment and view vibration measurements.</span></span>

<span data-ttu-id="36baf-111">Tworzona jest ocena stanu składników majątku.</span><span class="sxs-lookup"><span data-stu-id="36baf-111">Condition assessment is created on assets.</span></span> <span data-ttu-id="36baf-112">Przed wykonaniem procedury oceny warunków należy skonfigurować szablon oceny warunków dla danego typu składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="36baf-112">You set up a condition assessment template on an asset type before you carry out the condition assessment procedure.</span></span> <span data-ttu-id="36baf-113">Powodem stosowania szablonów do oceny stanu jest uniknięcie zmienności danych dotyczących podobnych składników majątku.</span><span class="sxs-lookup"><span data-stu-id="36baf-113">The reason for using templates for condition assessment is to avoid variation of condition data on similar assets.</span></span> <span data-ttu-id="36baf-114">Kolejność konfigurowania i używania oceny stanu w zarządzaniu składnikami majątku to: najpierw należy skonfigurować wymagane szablony oceny warunków.</span><span class="sxs-lookup"><span data-stu-id="36baf-114">The sequence for setting up and using condition assessment in Asset Management is: First you set up the required condition assessment templates.</span></span> <span data-ttu-id="36baf-115">Następnie skojarz szablony z typami składników majątku w formularzu **typy składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="36baf-115">Next, you associate templates with asset types in the **Asset types** form.</span></span> <span data-ttu-id="36baf-116">Na koniec można utworzyć rejestracje oceny warunku dla zasobu w formularzu **składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="36baf-116">Finally, you can create condition assessment registrations on an asset in the **Asset** form.</span></span>

## <a name="create-a-condition-assessment-template"></a><span data-ttu-id="36baf-117">Tworzenie szablonu oceny warunku</span><span class="sxs-lookup"><span data-stu-id="36baf-117">Create a condition assessment template</span></span>

1. <span data-ttu-id="36baf-118">Wybierz **Zarządzanie składnikami majątku** > **Ustawienia** > **Typy składników majątku** > **Ocena warunku**.</span><span class="sxs-lookup"><span data-stu-id="36baf-118">Select **Asset management** > **Setup** > **Asset types** > **Condition assessment**.</span></span>
2. <span data-ttu-id="36baf-119">Wybierz pozycję **Nowy**, aby utworzyć nowy szablon.</span><span class="sxs-lookup"><span data-stu-id="36baf-119">Select **New** to create a new template.</span></span>
3. <span data-ttu-id="36baf-120">Wstaw identyfikator szablonu w polu **Szablon**.</span><span class="sxs-lookup"><span data-stu-id="36baf-120">Insert and ID for the template in the **Template** field.</span></span>
4. <span data-ttu-id="36baf-121">Wstaw nazwę szablonu w polu **Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="36baf-121">Insert a name for the template in the **Name** field.</span></span>
5. <span data-ttu-id="36baf-122">Na skróconej karcie **Wiersze oceny warunku** dodaj wiersze wymagane do oceny warunku, w tym wybór odpowiedniego typu warunku i jednostkę miary.</span><span class="sxs-lookup"><span data-stu-id="36baf-122">On the **Condition assessment lines** FastFab, add the lines required for the condition assessment, including selection of the appropriate condition type and measurement unit.</span></span>
6. <span data-ttu-id="36baf-123">Na skróconej karcie **Typy składników majątku** dodaj typy składników majątku, dla których ma być używany ten szablon oceny warunku.</span><span class="sxs-lookup"><span data-stu-id="36baf-123">On the **Asset types** FastTab, add the asset types that should use the condition assessment template.</span></span>
7. <span data-ttu-id="36baf-124">W polach **Wiersze** i **Typy składników majątku** w grupie **Szczegóły** u góry ekranu zobaczysz wiersze oceny i typów składników majątku związanych z wybranym szablonem oceny warunku.</span><span class="sxs-lookup"><span data-stu-id="36baf-124">In the **Lines** and **Asset types** fields in the **Details** group at the top of the screen, you will see the number of assessment lines and asset types related to the selected condition assessment template.</span></span>


## <a name="create-condition-assessment-registration-on-an-asset"></a><span data-ttu-id="36baf-125">Tworzenie rejestracji oceny warunku dla składnika majątku</span><span class="sxs-lookup"><span data-stu-id="36baf-125">Create condition assessment registration on an asset</span></span>

1. <span data-ttu-id="36baf-126">Wybierz **Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Wszystkie składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="36baf-126">Select **Asset management** > **Common** > **Assets** > **All Assets**.</span></span>
2. <span data-ttu-id="36baf-127">Na liście wybierz składnik majątku, dla którego chcesz utworzyć rejestrację oceny warunku.</span><span class="sxs-lookup"><span data-stu-id="36baf-127">In the list, select the asset for which you want to create a condition assessment registration.</span></span>
3. <span data-ttu-id="36baf-128">Na karcie **Ogólne** kliknij przycisk **Ocena warunku**.</span><span class="sxs-lookup"><span data-stu-id="36baf-128">On the **General** tab, click **Condition assessment**.</span></span>
4. <span data-ttu-id="36baf-129">Kliknij przycisk **Nowy**, aby dodać nową rejestrację.</span><span class="sxs-lookup"><span data-stu-id="36baf-129">Click **New** to make a new registration.</span></span>
5. <span data-ttu-id="36baf-130">Wybierz datę oceny warunku w polu **Data.**</span><span class="sxs-lookup"><span data-stu-id="36baf-130">Select the date for the condition assessment in the **Date** field.</span></span>
6. <span data-ttu-id="36baf-131">Wybierz imię i nazwisko pracownika, który przeprowadził rejestrację oceny w polu **pracownik.**</span><span class="sxs-lookup"><span data-stu-id="36baf-131">Select the name of the worker who carried out the assessment registration in the **Worker** field.</span></span>
7. <span data-ttu-id="36baf-132">W polu **wiersze** jest widoczna liczba wierszy oceny, które zostały skonfigurowane w ramach oceny warunku.</span><span class="sxs-lookup"><span data-stu-id="36baf-132">In the **Lines** field, you see the number of assessment lines set up on the condition assessment.</span></span>
8. <span data-ttu-id="36baf-133">Wybierz szablon dla oceny warunku w polu **Szablon**.</span><span class="sxs-lookup"><span data-stu-id="36baf-133">Select a template for the condition assessment in the **Template** field.</span></span> <span data-ttu-id="36baf-134">Nazwa szablonu zostanie automatycznie wstawiona w polu **Nazwa**, a powiązane wiersze rejestracji zostaną wstawione na skróconej karcie **wiersze oceny warunków**.</span><span class="sxs-lookup"><span data-stu-id="36baf-134">The name of the template is automatically inserted in the **Name** field, and the related registration lines are inserted on the **Condition assessment lines** FastTab.</span></span>
9. <span data-ttu-id="36baf-135">Można wstawiać notatki odnoszące się do wybranej oceny warunku na skróconej karcie **Notatki**.</span><span class="sxs-lookup"><span data-stu-id="36baf-135">You can insert notes relating to the selected condition assessment on the **Notes** FastTab.</span></span>
10. <span data-ttu-id="36baf-136">Dla każdego wiersza oceny warunku wstaw dane pomiarowe w polu **Wartość**.</span><span class="sxs-lookup"><span data-stu-id="36baf-136">For each condition assessment line, insert measurement data in the **Value** field.</span></span>
11. <span data-ttu-id="36baf-137">Można wstawić komentarz odnoszący się do wybranego wiersza rejestracji na skróconej karcie **wiersze oceny warunków** > **pole komentarzy**.</span><span class="sxs-lookup"><span data-stu-id="36baf-137">You can insert a comment relating to the selected registration line on the **Condition assessment lines** FastTab > **Comments** field.</span></span> <span data-ttu-id="36baf-138">Dodanie komentarza do wiersza powoduje automatyczne zaznaczenie pola wyboru **Komentarz**.</span><span class="sxs-lookup"><span data-stu-id="36baf-138">If you add a comment on a line, the **Comment** check box is automatically selected.</span></span>

<span data-ttu-id="36baf-139">Po dokonaniu rejestracji oceny warunków dla składnika majątku można wydrukować raport oceny stanu.</span><span class="sxs-lookup"><span data-stu-id="36baf-139">After you have made a condition assessment registration on an asset, you can print a condition assessment report.</span></span>

>[!NOTE]
><span data-ttu-id="36baf-140">Można również zarejestrować oceny stanu w zleceniu pracy (**Zarządzanie składnikiem majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** > **Ocena warunku**.)</span><span class="sxs-lookup"><span data-stu-id="36baf-140">You can also register condition assessment on a work order (**Asset management** > **Common** > **Work orders** > **All Work orders** > **Condition assessment** button.)</span></span>
