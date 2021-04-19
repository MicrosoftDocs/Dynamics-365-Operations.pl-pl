---
title: Włączanie integracji Dynamics 365 Commerce i Microsoft Teams
description: W tym temacie opisano sposób włączania integracji Microsoft Dynamics 365 Commerce i Microsoft Teams.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c0dbf7a3c7fa3532e35cac240c1abb8adbdbe489
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842724"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a><span data-ttu-id="15a72-103">Włączanie integracji Dynamics 365 Commerce i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="15a72-103">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="15a72-104">W tym temacie opisano sposób włączania integracji Microsoft Dynamics 365 Commerce i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="15a72-104">This topic describes how to enable Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

<span data-ttu-id="15a72-105">Aby wyposażyć Teams w informacje z Dynamics 365 Commerce i zsynchronizować funkcje zarządzania zadaniami między Teams i aplikacją punktu sprzedaży (POS), musisz włączyć funkcje integracji w centrali Commerce.</span><span class="sxs-lookup"><span data-stu-id="15a72-105">To provision Teams with information from Dynamics 365 Commerce and synchronize the task management features between Teams and the point of sale (POS) application, you must enable the integration features in Commerce headquarters.</span></span>

> [!NOTE]
> <span data-ttu-id="15a72-106">Włączając integrację Teams, wyrażasz zgodę na udostępnianie swoich danych Teams.</span><span class="sxs-lookup"><span data-stu-id="15a72-106">When you enable Teams integration, you consent to share your data with Teams.</span></span> <span data-ttu-id="15a72-107">Dane, które są udostępniane Teams, mogą znajdować się w innym kraju niż Twoje dane Commerce i mogą podlegać innym standardom zgodności.</span><span class="sxs-lookup"><span data-stu-id="15a72-107">Data that is shared with Teams might reside in a different country than your Commerce data, and it might be subject to different compliance standards.</span></span> <span data-ttu-id="15a72-108">Aby uzyskać więcej informacji, zobacz temat [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="15a72-108">For more information, see the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="15a72-109">Aby uzyskać więcej informacji o zasadach zachowania poufności informacji firmy Microsoft, zobacz [Zasady zachowania poufności informacji firmy Microsoft](https://aka.ms/privacy).</span><span class="sxs-lookup"><span data-stu-id="15a72-109">For information about Microsoft privacy policies, see the [Microsoft Privacy Statement](https://aka.ms/privacy).</span></span>

## <a name="enable-teams-integration"></a><span data-ttu-id="15a72-110">Włączanie integracji Teams</span><span class="sxs-lookup"><span data-stu-id="15a72-110">Enable Teams integration</span></span>

<span data-ttu-id="15a72-111">Zanim będzie można włączyć integrację Microsoft Teams z Commerce, musisz zarejestrować aplikację Teams u dzierżawcy w Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="15a72-111">Before you can enable Microsoft Teams integration with Commerce, you must register the Teams application with your tenant in the Azure portal.</span></span>

<span data-ttu-id="15a72-112">Aby zarejestrować aplikację Teams u dzierżawcy w witrynie Azure Portal, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="15a72-112">To register the Teams application with your tenant in the Azure portal, follow these steps.</span></span>

1. <span data-ttu-id="15a72-113">Wykonaj kroki w narzędziu [Quickstart: Zarejestruj aplikację na platformie tożsamości firmy Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app), aby zarejestrować aplikację Teams w Twojej dzierżawie w portalu Azure.</span><span class="sxs-lookup"><span data-stu-id="15a72-113">Follow the steps in [Quickstart: Register an app in the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app) to register the Teams application with your tenant in the Azure portal.</span></span>
1. <span data-ttu-id="15a72-114">Skopiuj wartość **Identyfikator aplikacji (klienta)** ze strony **Przegląd** zarejestrowanej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="15a72-114">Copy the **Application (client) ID** value from the **Overview** page for the registered app.</span></span> <span data-ttu-id="15a72-115">Użyjesz tej wartości, aby włączyć integrację Teams w centrali Commerce.</span><span class="sxs-lookup"><span data-stu-id="15a72-115">You will use this value to enable Teams integration in Commerce headquarters.</span></span>
1. <span data-ttu-id="15a72-116">Umożliwia skopiowanie wartości certyfikatu wprowadzonej podczas [dodawana do certyfikatu](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-certificate) w kroku 1.</span><span class="sxs-lookup"><span data-stu-id="15a72-116">Copy the certificate value that was entered when you [added a certificate](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-certificate) in step 1.</span></span> <span data-ttu-id="15a72-117">Certyfikat jest również znany jako klucz publiczny lub klucz aplikacji.</span><span class="sxs-lookup"><span data-stu-id="15a72-117">The certificate is also known as the public key or application key.</span></span> <span data-ttu-id="15a72-118">Użyjesz tej wartości, aby włączyć integrację Teams w centrali Commerce.</span><span class="sxs-lookup"><span data-stu-id="15a72-118">You will use this value to enable Teams integration in Commerce headquarters.</span></span>

<span data-ttu-id="15a72-119">Aby włączyć integrację Teams w centrali Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="15a72-119">To enable Teams integration in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="15a72-120">Przejdź do opcji **Retail i Commerce \> Konfiguracja kanału \> Grupy realizacji Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="15a72-120">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams integration configuration**.</span></span>
1. <span data-ttu-id="15a72-121">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="15a72-121">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="15a72-122">Ustaw opcję **Włącz integracje Microsoft Teams** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="15a72-122">Set the **Enable Microsoft Teams integration** option to **Yes**.</span></span>
1. <span data-ttu-id="15a72-123">W polach **Identyfikator aplikacji** i **Klucz aplikacji** wprowadź wartości uzyskane podczas rejestrowania aplikacji Teams w portalu Azure.</span><span class="sxs-lookup"><span data-stu-id="15a72-123">In the **Application ID** and **Application key** fields, enter the values you obtained when you registered the Teams application in the Azure portal.</span></span>
1. <span data-ttu-id="15a72-124">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="15a72-124">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="15a72-125">Poniższa ilustracja przedstawia przykład konfiguracji integracji Teams w centrali Commerce.</span><span class="sxs-lookup"><span data-stu-id="15a72-125">The following illustration shows an example of the configuration of Teams integration in Commerce headquarters.</span></span>

![Konfiguracja integracji zespołów w Commerce Headquarters](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

## <a name="disable-teams-integration"></a><span data-ttu-id="15a72-127">Wyłączanie integracji Teams</span><span class="sxs-lookup"><span data-stu-id="15a72-127">Disable Teams integration</span></span>

<span data-ttu-id="15a72-128">Aby wyłączyć integrację Microsoft Teams w centrali Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="15a72-128">To disable Microsoft Teams integration in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="15a72-129">Przejdź do opcji **Retail i Commerce \> Konfiguracja kanału \> Grupy realizacji Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="15a72-129">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="15a72-130">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="15a72-130">On the Action Pane, select **Edit**.</span></span>
3. <span data-ttu-id="15a72-131">Ustaw opcję **Włącz integracje Microsoft Teams** na **Nie**.</span><span class="sxs-lookup"><span data-stu-id="15a72-131">Set the **Enable Microsoft Teams integration** option to **No**.</span></span>
4. <span data-ttu-id="15a72-132">Wyczyść wartości pól **Identyfikator aplikacji** i **Klucz aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="15a72-132">Clear the values from the **Application ID** and **Application Key** fields.</span></span>
1. <span data-ttu-id="15a72-133">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="15a72-133">On the Action Pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="15a72-134">Po wyłączeniu integracji Teams z aplikacją Commerce terminale POS nie będą już wyświetlać zadań opublikowanych z aplikacji Teams.</span><span class="sxs-lookup"><span data-stu-id="15a72-134">After you disable Teams integration with Commerce, POS terminals will no longer show tasks that are published from the Teams application.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="15a72-135">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="15a72-135">Additional resources</span></span>

[<span data-ttu-id="15a72-136">Omówienie integracji Dynamics 365 Commerce i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="15a72-136">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="15a72-137">Obsługa Microsoft Teams z Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="15a72-137">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="15a72-138">Synchronizowanie zarządzania zadaniami między punktami sprzedaży usług Microsoft Teams i Dynamics 365 Commerce POS</span><span class="sxs-lookup"><span data-stu-id="15a72-138">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="15a72-139">Zarządzanie rolami użytkowników w usłudze Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="15a72-139">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="15a72-140">Mapowanie sklepów i zespołów w przypadku, gdy istnieją już inne zespoły w usłudze Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="15a72-140">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="15a72-141">Integracja z usługami Dynamics 365 Commerce i Microsoft Teams - FAQ</span><span class="sxs-lookup"><span data-stu-id="15a72-141">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
