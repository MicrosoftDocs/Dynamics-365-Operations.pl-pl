---
title: Tworzenie hierarchii modelowania organizacji dla organizacji B2B
description: W tym temacie opisano sposób tworzenia hierarchii modelowania organizacyjnego dla organizacji typu B2B (business-to-business).
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 91cb01637faa69bd3c7fefefae69c60cb948510e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211232"
---
# <a name="create-org-modeling-hierarchies-for-b2b-organizations"></a><span data-ttu-id="2d86f-103">Tworzenie hierarchii modelowania organizacji dla organizacji B2B</span><span class="sxs-lookup"><span data-stu-id="2d86f-103">Create org modeling hierarchies for B2B organizations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2d86f-104">W tym temacie opisano sposób tworzenia hierarchii modelowania organizacyjnego dla organizacji typu B2B (business-to-business) w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2d86f-104">This topic describes how to create organizational modeling hierarchies for business-to-business (B2B) organizations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="2d86f-105">W centrali Commerce organizacje partnerów biznesowych są reprezentowane przez jednostki hierarchii klientów i odbiorców.</span><span class="sxs-lookup"><span data-stu-id="2d86f-105">In Commerce headquarters, business partner organizations are represented by customer and customer hierarchy entities.</span></span> <span data-ttu-id="2d86f-106">Organizacja partnera biznesowego i jej użytkownicy są reprezentowani jako klienci, a hierarchie klientów służą do kojarzenia tych klientów ze sobą.</span><span class="sxs-lookup"><span data-stu-id="2d86f-106">The business partner organization and its users are represented as customers, and customer hierarchies are used to associate those customers with each other.</span></span>

<span data-ttu-id="2d86f-107">Gdy prośba partnera biznesowego o dołączenie do witryny handlu elektronicznego B2B zostanie zatwierdzona, wykonywane są następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="2d86f-107">When a business partner request to join a B2B e-commerce site is approved, the following actions are performed:</span></span>

- <span data-ttu-id="2d86f-108">Ponadto w systemie są tworzone dwa nowe rekordy odbiorcy: rekord odbiorcy organizacji **Typu organizacji** partnera biznesowego i rekord klienta **typu Osoba** dla zleceniodawcy (to znaczy użytkownika partnera biznesowego, który przesłał żądanie).</span><span class="sxs-lookup"><span data-stu-id="2d86f-108">Two new customer records are created in the system: a **Type Organization** customer record for the business partner organization and a **Type Person** customer record for the requestor (that is, the business partner user who submitted the request).</span></span>
- <span data-ttu-id="2d86f-109">Nowy rekord hierarchii odbiorcy jest tworzony w **Odbiorca \> Hierarchia odbiorców**.</span><span class="sxs-lookup"><span data-stu-id="2d86f-109">A new customer hierarchy record is created under **Customer \> Customer hierarchy**.</span></span> <span data-ttu-id="2d86f-110">Ten rekord ma następujące właściwości nagłówka:</span><span class="sxs-lookup"><span data-stu-id="2d86f-110">This record has the following header properties:</span></span>

    - <span data-ttu-id="2d86f-111">**Identyfikator hierarchii odbiorcy** – unikatowy identyfikator hierarchii odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="2d86f-111">**Customer hierarchy ID** – A unique ID for the customer hierarchy.</span></span> <span data-ttu-id="2d86f-112">Ten identyfikator używa sekwencji numerów zdefiniowanej w parametrach współdzielonych aplikacji Commerce w Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="2d86f-112">This ID uses the number sequence that is defined in Commerce shared parameters in Commerce headquarters.</span></span>
    - <span data-ttu-id="2d86f-113">**Nazwa** — nazwa organizacji partnera biznesowego, określona w żądaniu przysyłania.</span><span class="sxs-lookup"><span data-stu-id="2d86f-113">**Name** – The organization name of the business partner, as specified in the onboarding request.</span></span>
    - <span data-ttu-id="2d86f-114">**Cel** — właściwość jest ustawiona na wstępnie zdefiniowaną wartość **organizacji B2B**.</span><span class="sxs-lookup"><span data-stu-id="2d86f-114">**Purpose** – This property is set to the predefined value **B2B organization**.</span></span>
    - <span data-ttu-id="2d86f-115">**Organizacja** — Identyfikator klienta partnera biznesowego.</span><span class="sxs-lookup"><span data-stu-id="2d86f-115">**Organization** – The customer ID of the business partner.</span></span>

<span data-ttu-id="2d86f-116">Oto szczegóły rekordu hierarchii odbiorcy:</span><span class="sxs-lookup"><span data-stu-id="2d86f-116">Here are the details of the customer hierarchy record:</span></span>

- <span data-ttu-id="2d86f-117">Rekord odbiorcy dla żądacy jest skojarzony z hierarchią odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="2d86f-117">The customer record of the requestor is associated with the customer hierarchy.</span></span>
- <span data-ttu-id="2d86f-118">Rola administratora jest skojarzona z żądaniem.</span><span class="sxs-lookup"><span data-stu-id="2d86f-118">The administrator role is associated with the requestor.</span></span>

<span data-ttu-id="2d86f-119">Gdy administrator dodaje więcej użytkowników do organizacji partnera biznesowego w witrynie B2B, w programie Commerce Headquarters jest tworzony nowy rekord odbiorcy dla każdego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2d86f-119">When the administrator adds more users are to the business partner organization on a B2B site, a new customer record for each user is created in Commerce headquarters.</span></span> <span data-ttu-id="2d86f-120">Ten rekord odbiorcy jest również dodawany do odpowiedniego rekordu hierarchii odbiorcy dla partnera biznesowego i ma rolę „użytkownika”</span><span class="sxs-lookup"><span data-stu-id="2d86f-120">This customer record is also added to the relevant customer hierarchy record for the business partner and has the role of a "user."</span></span>

> [!NOTE]
> <span data-ttu-id="2d86f-121">W większości przypadków odpowiednie wartości właściwości wszystkich rekordów klientów w hierarchii powinny być zgodne.</span><span class="sxs-lookup"><span data-stu-id="2d86f-121">In most cases, the corresponding property values of all customer records in a hierarchy should match.</span></span> <span data-ttu-id="2d86f-122">Na przykład, ponieważ wszyscy użytkownicy partnerów biznesowych powinni otrzymywać podobne ceny produktów, ich grupy cenowe i powiązane konfiguracje powinny być zgodne.</span><span class="sxs-lookup"><span data-stu-id="2d86f-122">For example, because all business partner users should get similar prices for products, their price group and associated configurations should match.</span></span> <span data-ttu-id="2d86f-123">Jednak system nie wymusza tej spójności.</span><span class="sxs-lookup"><span data-stu-id="2d86f-123">However, the system doesn't enforce this consistency.</span></span> <span data-ttu-id="2d86f-124">W związku z tym odpowiedni użytkownicy Commerce headquarters są odpowiedzialni za zapewnienie, że wartości właściwości i konfiguracje są zgodne dla wszystkich klientów w danej hierarchii.</span><span class="sxs-lookup"><span data-stu-id="2d86f-124">Therefore, the relevant Commerce headquarters users are responsible for ensuring that the property values and configurations match for all customers in a given hierarchy.</span></span>

<span data-ttu-id="2d86f-125">Użytkownicy Commerce Headquarters mogą przeglądać wartości właściwości dla wszystkich rekordów klientów w hierarchii w widoku obok siebie.</span><span class="sxs-lookup"><span data-stu-id="2d86f-125">Commerce headquarters users can look at the property values for all customer records in the hierarchy in a side-by-side view.</span></span> <span data-ttu-id="2d86f-126">Wybierz odpowiednie właściwości rekordu odbiorcy, wybierając nazwy kart z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="2d86f-126">Select the relevant customer record properties by selecting the tab names on the drop-down menu.</span></span> <span data-ttu-id="2d86f-127">Użytkownicy mogą bezpośrednio wyświetlać i edytować wartości właściwości z tego widoku.</span><span class="sxs-lookup"><span data-stu-id="2d86f-127">Users can directly view and edit the property values from this view.</span></span> <span data-ttu-id="2d86f-128">Alternatywnie, jeśli chcesz zastosować wszystkie wartości z rekordu klienta administratora do wszystkich rekordów klientów użytkownika, wybierz opcję **Zastąp** w szczegółach hierarchii klientów.</span><span class="sxs-lookup"><span data-stu-id="2d86f-128">Alternatively, if you want to apply all the values from the administrator customer record to all the user customer records, select **Override** in the customer hierarchy details.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2d86f-129">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="2d86f-129">Additional resources</span></span>

[<span data-ttu-id="2d86f-130">Konfigurowanie witryny handlu elektornicznego B2B</span><span class="sxs-lookup"><span data-stu-id="2d86f-130">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="2d86f-131">Zarządzaj użytkownikami partnerów biznesowych w witrynach handlu elektronicznego B2B</span><span class="sxs-lookup"><span data-stu-id="2d86f-131">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="2d86f-132">Konfigurowanie metody płatności na konto odbiorcy dla witryn handlu elektronicznego B2B</span><span class="sxs-lookup"><span data-stu-id="2d86f-132">Configure the customer account payment method for B2B e-commerce sites</span></span>](payment-method.md)

[<span data-ttu-id="2d86f-133">Ustawianie limitów ilości produktów dla witryn B2B handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="2d86f-133">Set product quantity limits for B2B e-commerce sites</span></span>](quantity-limits.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]