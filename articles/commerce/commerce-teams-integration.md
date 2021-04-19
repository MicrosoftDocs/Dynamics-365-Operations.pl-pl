---
title: Omówienie integracji Dynamics 365 Commerce i Microsoft Teams
description: Ten temat zawiera omówienie integracji Microsoft Dynamics 365 Commerce i Microsoft Teams.
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
ms.openlocfilehash: 3b7872757815d4eec0393e8b1c8c6ff5467e9473
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842723"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-overview"></a><span data-ttu-id="f4244-103">Omówienie integracji Dynamics 365 Commerce i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f4244-103">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="f4244-104">Ten temat zawiera omówienie integracji Microsoft Dynamics 365 Commerce i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f4244-104">This topic presents an overview of Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

<span data-ttu-id="f4244-105">Dynamics 365 Commerce integruje się z Teams, aby pomagać klientom i ich pracownikom w zwiększaniu produktywności dzięki zsynchronizowaniu zarządzania zadaniami między tymi dwiema aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="f4244-105">Dynamics 365 Commerce is integrating with Teams to help customers and their employees improve productivity by synchronizing task management between the two applications.</span></span> <span data-ttu-id="f4244-106">Bezproblemowa zarządzanie zadaniami, dzięki integracji z usługami Commerce and Teams, menedżerowie sklepu i pracownicy mogą tworzyć listy zadań, przypisywać zadania do wielu sklepów i śledzić stan zadań w różnych sklepach z każdej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f4244-106">The seamless task management that Commerce and Teams integration provides lets store managers and employees create task lists, assign tasks to multiple stores, and track the status of tasks across stores, from either application.</span></span>

<span data-ttu-id="f4244-107">Integracja z usługami Commerce and Teams jest dostępna od wersji 10.0.18 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f4244-107">Commerce and Teams integration is available as of the Commerce version 10.0.18 release.</span></span>

## <a name="key-features"></a><span data-ttu-id="f4244-108">Najważniejsze funkcje</span><span class="sxs-lookup"><span data-stu-id="f4244-108">Key features</span></span>

<span data-ttu-id="f4244-109">Poniżej przedstawiono niektóre najważniejsze funkcje dostępne dzięki integracji Commerce i Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="f4244-109">Here are some of the key features that the Commerce and Microsoft Teams integration provides:</span></span>

- <span data-ttu-id="f4244-110">Obsługuj Teams, korzystając z dobrze zdefiniowanych informacji z aplikacji Commerce, takich jak struktura organizacyjna i informacje o sklepach, pracownikach, uprawnieniach i kontekście biznesowym.</span><span class="sxs-lookup"><span data-stu-id="f4244-110">Provision Teams by taking advantage of well-defined information from Commerce, such as the organizational structure and information about stores, workers, permissions, and business context.</span></span>
- <span data-ttu-id="f4244-111">Z łatwością synchronizuj bieżące zmiany (na przykład dodawanie nowych sklepów lub zatrudnianie nowych pracowników) między aplikacjami Commerce i Teams, ale zachowaj Commerce jako główne źródło danych o strukturze organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="f4244-111">Easily synchronize ongoing changes (for example, the addition of new stores or hiring of new employees) between Commerce and Teams, but keep Commerce as the master source of organizational structure data.</span></span>
- <span data-ttu-id="f4244-112">Zintegruj zarządzanie zadaniami między aplikacjami Commerce i Teams, aby ułatwić pracownikom sklepów, kierownikom sklepów, kierownikom regionalnym i kierownikom ds. Komunikacji zarządzanie zadaniami z dowolnej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f4244-112">Integrate task management between Commerce and Teams to help store workers, store managers, regional managers, and communications managers handle task management from either application.</span></span>

## <a name="prerequisites-for-using-integration-features"></a><span data-ttu-id="f4244-113">Wymagania wstępne dotyczące używania funkcji integracji</span><span class="sxs-lookup"><span data-stu-id="f4244-113">Prerequisites for using integration features</span></span>

<span data-ttu-id="f4244-114">Przed rozpoczęciem korzystania z funkcji integracji Microsoft Teams muszą zostać spełnione następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="f4244-114">The following prerequisites must be in place before you can start to use Microsoft Teams integration features:</span></span>

- <span data-ttu-id="f4244-115">Licencja na oprogramowanie Microsoft 365 Business Standard (ta licencja zawiera Teams.)</span><span class="sxs-lookup"><span data-stu-id="f4244-115">Microsoft 365 Business Standard License (This license includes Teams.)</span></span>
- <span data-ttu-id="f4244-116">Azure Active Directory (Azure AD) konta wszystkich menedżerów sklepów i pracowników</span><span class="sxs-lookup"><span data-stu-id="f4244-116">Azure Active Directory (Azure AD) accounts for all store managers and workers</span></span>
- <span data-ttu-id="f4244-117">Systemy punktu sprzedaży, które są skonfigurowane z uwierzytelnianiem Azure AD</span><span class="sxs-lookup"><span data-stu-id="f4244-117">Point of sale (POS) systems that are configured with Azure AD authentication</span></span>

## <a name="conceptual-architecture"></a><span data-ttu-id="f4244-118">Architektura pojęć</span><span class="sxs-lookup"><span data-stu-id="f4244-118">Conceptual architecture</span></span>

<span data-ttu-id="f4244-119">Na poniższej ilustracji przedstawiono architekturę pojęć i integrację Dynamics 365 Commerce i Microsoft Teams, w których przykładem jest sklep San Francisco.</span><span class="sxs-lookup"><span data-stu-id="f4244-119">The following illustration shows the conceptual architecture of Dynamics 365 Commerce and Microsoft Teams integration, using a San Francisco store as an example.</span></span> <span data-ttu-id="f4244-120">Zarówno Teams, jak i aplikacja Commerce POS używają Microsoft Planner jako repozytorium, dzięki czemu zadania publikowane z Teams pojawiają się w aplikacji POS, a zadania ad hoc utworzone przez kierowników sklepów w aplikacji POS pojawiają się w aplikacji Teams, co skutkuje bezproblemowym zarządzaniem zadaniami między aplikacjami .</span><span class="sxs-lookup"><span data-stu-id="f4244-120">Both Teams and the Commerce POS application use Microsoft Planner as a repository so that tasks published from Teams appear in the POS application and ad hoc tasks created by store managers in the POS application appear in Teams, resulting in a seamless task management experience between the applications.</span></span>    

![Architektura integracji z usługami Commerce i Teams](media/d365-commerce-teams-integration-conceptual-architecture.png)

## <a name="additional-resources"></a><span data-ttu-id="f4244-122">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f4244-122">Additional resources</span></span>

[<span data-ttu-id="f4244-123">Włączanie integracji Dynamics 365 Commerce i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f4244-123">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="f4244-124">Obsługa Microsoft Teams z Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f4244-124">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="f4244-125">Synchronizowanie zarządzania zadaniami między punktami sprzedaży usług Microsoft Teams i Dynamics 365 Commerce POS</span><span class="sxs-lookup"><span data-stu-id="f4244-125">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="f4244-126">Zarządzanie rolami użytkowników w usłudze Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f4244-126">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="f4244-127">Mapowanie sklepów i zespołów w przypadku, gdy istnieją już inne zespoły w usłudze Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f4244-127">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="f4244-128">Integracja z usługami Dynamics 365 Commerce i Microsoft Teams - FAQ</span><span class="sxs-lookup"><span data-stu-id="f4244-128">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
