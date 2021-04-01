---
title: Konfiguracje wniosku o nowego dostawcę
description: W tym temacie opisano pola, których wypełnienie jest wymagane w nowym wniosku o nowego dostawcę.
author: RichardLuan
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationConfig
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 61ef9ba4eb683fea030f06b3bacf687d7f146de4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246580"
---
# <a name="vendor-request-configurations"></a><span data-ttu-id="7425d-103">Konfiguracje wniosku o nowego dostawcę</span><span class="sxs-lookup"><span data-stu-id="7425d-103">Vendor request configurations</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="7425d-104">Aby utworzyć wniosek o nowego dostawcę, osoba kontaktowa dostawcy musi ukończyć kreatora rejestracji potencjalnego dostawcy.</span><span class="sxs-lookup"><span data-stu-id="7425d-104">To complete a vendor request, a vendor contact person must complete the prospective vendor registration wizard.</span></span>

<span data-ttu-id="7425d-105">W formularzu **Konfiguracje wniosku o nowego dostawcę** można utworzyć profile określające wymagane i widoczne pola w kreatorze rejestracji potencjalnego dostawcy.</span><span class="sxs-lookup"><span data-stu-id="7425d-105">In the **Vendor request configurations** form, you can create profiles that specify required fields and visible fields in the prospective vendor registration wizard.</span></span>

<span data-ttu-id="7425d-106">Kreator rejestracji dostawcy rozpocznie od pytania użytkownika-potencjalnego dostawcy o kraj/region, w którym dostawca prowadzi działalność.</span><span class="sxs-lookup"><span data-stu-id="7425d-106">The vendor registration wizard will start out by asking the prospective vendor user which country/region the vendor is doing business in.</span></span> <span data-ttu-id="7425d-107">Ta informacja wpływa na wybór odpowiedniej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="7425d-107">This information determines the applicable configuration.</span></span> <span data-ttu-id="7425d-108">W przypadku niezdefiniowania określonej konfiguracji dla kraju/regionu zostanie użyta konfiguracja domyślna.</span><span class="sxs-lookup"><span data-stu-id="7425d-108">If no specific configuration is defined for a country/region, a default configuration will be used.</span></span>

### <a name="set-up-a-vendor-request-configuration"></a><span data-ttu-id="7425d-109">Definiowanie konfiguracji wniosku o nowego dostawcę</span><span class="sxs-lookup"><span data-stu-id="7425d-109">Set up a vendor request configuration</span></span>

<span data-ttu-id="7425d-110">Domyślnie konfiguracja dostawcy jest dostępna w formularzu konfiguracji wniosku o nowego dostawcę.</span><span class="sxs-lookup"><span data-stu-id="7425d-110">By default, there is a vendor configuration available in the Vendor request configurations form.</span></span>

<span data-ttu-id="7425d-111">Wybór kraju/regionów dla konfiguracji domyślnej jest niemożliwy, dlatego nie można wprowadzić zmian w sekcji **Kraje/regiony**.</span><span class="sxs-lookup"><span data-stu-id="7425d-111">It is not possible to select country/regions for the default configuration, so the **Countries/regions** section cannot be changed.</span></span>

1. <span data-ttu-id="7425d-112">Kliknij kolejno opcje **Zaopatrzenie i sourcing** > **Konfiguracja** > **Dostawcy**, a następnie kliknij opcję **Konfiguracje wniosku o nowego dostawcę**.</span><span class="sxs-lookup"><span data-stu-id="7425d-112">Click **Procurement and sourcing** > **Setup** > **Vendors**, and then click **Vendor request configurations**.</span></span>
2. <span data-ttu-id="7425d-113">Kliknij kartę **Pola** , aby ustawić stan wymienionych pól.</span><span class="sxs-lookup"><span data-stu-id="7425d-113">Click the **Fields** tab to set the status of the listed fields.</span></span>
3. <span data-ttu-id="7425d-114">Ukryte (niewidoczne)</span><span class="sxs-lookup"><span data-stu-id="7425d-114">Hidden (Not visible)</span></span>
4. <span data-ttu-id="7425d-115">Wyświetlane (widoczne, ale nieobowiązkowe)</span><span class="sxs-lookup"><span data-stu-id="7425d-115">Displayed (Visible but not mandatory)</span></span>
5. <span data-ttu-id="7425d-116">Wymagane (widoczne i obowiązkowe)</span><span class="sxs-lookup"><span data-stu-id="7425d-116">Required (Visible and mandatory)</span></span>
6. <span data-ttu-id="7425d-117">Kliknij kartę **Zawartość**, aby określić, czy tekst ma być widoczny w kreatorze oraz czy ma być dostępne potwierdzenie, które potencjalny dostawca musi zaakceptować przed przejściem do następnego krok w kreatorze.</span><span class="sxs-lookup"><span data-stu-id="7425d-117">Click the **Content** tab to specify if text is going to be shown on the wizard and if there should be an acknowledgement that the prospective vendor user must accept this before moving to the next step in the wizard.</span></span> <span data-ttu-id="7425d-118">Potwierdzenie będzie wymagane w przypadku wszystkich warunków i zasad, które użytkownik musi zaakceptować w celu kontynuacji.</span><span class="sxs-lookup"><span data-stu-id="7425d-118">The acknowledgement will be requested for any terms and conditions that the user must accept to continue.</span></span>

<span data-ttu-id="7425d-119">Można także wprowadzić komunikat potwierdzenia, który zostanie wyświetlony po zakończeniu pracy kreatora. Można też dodać co najmniej jeden kwestionariusz.</span><span class="sxs-lookup"><span data-stu-id="7425d-119">You can also enter a confirmation message that will be displayed when the wizard is finalized, and you can add one or more questionnaires.</span></span>

### <a name="create-a-vendor-configuration-for-a-specific-countryregion"></a><span data-ttu-id="7425d-120">Tworzenie konfiguracji dostawcy dla określonego kraju/regionu</span><span class="sxs-lookup"><span data-stu-id="7425d-120">Create a vendor configuration for a specific country/region</span></span>
1.  <span data-ttu-id="7425d-121">Kliknij kolejno opcje **Zaopatrzenie i sourcing** > **Konfiguracja** > **Dostawcy**, a następnie kliknij opcję **Konfiguracje wniosku o nowego dostawcę**.</span><span class="sxs-lookup"><span data-stu-id="7425d-121">Click **Procurement and sourcing** > **Setup** > **Vendors**, and then click **Vendor request configurations**.</span></span>
2.  <span data-ttu-id="7425d-122">Kliknij przycisk **Nowy**, aby utworzyć nową konfigurację i podaj jej nazwę.</span><span class="sxs-lookup"><span data-stu-id="7425d-122">Click **New** to create a new configuration, and provide a name for the configuration.</span></span>
3.  <span data-ttu-id="7425d-123">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="7425d-123">Click **Save**.</span></span>
4.  <span data-ttu-id="7425d-124">Otwórz kartę **Kraj/regiony**, aby wybrać kraj/region, dla którego ma zostać użyta konfiguracja.</span><span class="sxs-lookup"><span data-stu-id="7425d-124">Open the **Country/regions** tab to select the country/region that the configuration should be used for.</span></span>
5.  <span data-ttu-id="7425d-125">Dokończ konfigurację, postępując zgodnie ze wskazówkami dotyczącymi konfiguracji domyślnej.</span><span class="sxs-lookup"><span data-stu-id="7425d-125">Complete the configuration by following the guidelines for the default configuration.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]