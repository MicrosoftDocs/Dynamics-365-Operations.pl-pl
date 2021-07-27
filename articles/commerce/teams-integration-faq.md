---
title: Integracja z usługami Dynamics 365 Commerce i Microsoft Teams — często zadawane pytania
description: Ten temat zawiera odpowiedzi dotyczące często zadawanych pytań dotyczących integracji Microsoft Dynamics 365 Commerce i Microsoft Teams.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 45decb55ce5cf3399f48034df367e1565ab689bf
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6347447"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-faq"></a>Integracja z usługami Dynamics 365 Commerce i Microsoft Teams — często zadawane pytania

[!include [banner](includes/banner.md)]

Ten temat zawiera odpowiedzi dotyczące często zadawanych pytań dotyczących integracji Microsoft Dynamics 365 Commerce i Microsoft Teams.

### <a name="who-in-the-store-becomes-an-owner-of-a-team-while-provisioning-teams-from-commerce"></a>Kto w sklepie staje się właścicielem zespołu podczas inicjowania obsługi Teams z usług Commerce? 

Wszyscy menedżerowie sklepu są automatycznie dodawana jako właściciele do odpowiedniej grupy grupę kierownicy, co oznacza, że mogą wykonywać takie operacje, jak dodawanie kanału prywatnego oraz dodawanie lub usuwanie członków. 

### <a name="how-do-i-assign-the-communications-manager-role-to-an-employee-in-commerce-headquarters"></a>Jak przypisać rolę „kierownik ds. komunikacji” do pracownika e-mail w Commerce headquarters? 

Kierownicy ds. komunikacji w Microsoft Teams mogą tworzyć i publikować listy zadań. Pracownicy organizacji, którzy muszą zostać menedżerami komunikacji, muszą mieć przypisaną rolę „kierownik ds. zadań sieci sprzedaży” w programie Commerce Headquarters.

Aby przypisać rolę menedżera zadań sieci sprzedaży do pracownika w programie Commerce Headquarters, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Retail and Commerce \> Pracownicy \> Użytkownicy**.
1. Wybierz pracownika.
1. Na karcie skróconej **Role użytkownika** wybierz opcję **Przypisz role**.
1. W oknie dialogowym **Przypisz role do użytkownika** wybierz rolę **Menedżer zadań sieci sprzedaży**, a następnie kliknij przycisk **OK**.

### <a name="how-do-i-make-a-specific-organization-hierarchy-available-to-upload-into-microsoft-teams"></a>Jak udostępnić do przekazania do Microsoft Teams określoną hierarchię organizacyjną?

W programie Commerce Headquarters hierarchia każdej organizacji jest skojarzona z jednym lub większą ich celem. Upewnij się, że z hierarchią, w której mają być obsługiwane usługi Microsoft Teams, jest skojarzony cel **Raportowania sieci sprzedaży**, tak jak pokazano na poniższym przykładzie. 

![Przykład celu hierarchii organizacyjnej w programie Commerce Headquarters.](media/d365-commerce-organization-hierarchies-purpose.png)

### <a name="how-do-i-enable-retail-store-workers-to-sign-in-to-commerce-point-of-sale-pos-using-azure-active-directory-azure-ad"></a>Jak umożliwić pracownikom sklepu detalicznego logowanie się do usługi Commerce punkt sprzedaży (POS) przy użyciu Azure Active Directory (Azure AD)?

Aby uzyskać informacje dotyczące konfigurowania funkcji logowania w programie Commerce POS do używania uwierzytelniania Azure AD, zobacz temat [Włączanie uwierzytelniania Azure Active Directory przy loganiu się do POS](aad-pos-logon.md)..

### <a name="how-do-i-map-stores-and-corresponding-teams-in-commerce-headquarters-if-my-organization-has-already-created-teams-in-microsoft-teams"></a>Jak mapować sklepy i odpowiadające im zespoły w programie Commerce Headquarters, jeśli w programie Commerce Headquarters moja organizacja utworzyła już zespoły Microsoft Teams.

Aby uzyskać informacje dotyczące mapowania sklepów i zespołów na istniejące zespoły, zobacz temat [Mapowanie sklepów i odpowiednich zespołów, jeśli organizacja ma już istniejące zespoły w Microsoft Teams](map-stores-existing-teams.md).

### <a name="how-do-i-clear-the-microsoft-graph-api-token-stored-in-the-session-storage"></a>Jak wyczyścić token interfejsu API programu Microsoft Graph przechowywany w magazynie sesji?

Użytkownik, który zalogował się do punktu sprzedaży (POS) za pomocą konta Azure Active Directory (Azure AD), powinien wylogować się z punktu sprzedaży lub zamknąć aplikację, aby wyczyścić magazyn sesji. 

> [!TIP]
> Zaleca się, aby pracownicy sklepu zawsze zablokowali terminal w aplikacji pos lub wylogowywają się z sesji, gdy terminal nie jest używany. 

### <a name="what-happens-if-a-store-doesnt-have-store-managers"></a>Co się stanie, jeśli sklep nie ma kierowników sklepu?

Jeśli sklep nie ma menedżerów, grupa zespołu nie zostanie utworzona dla sklepu ani w aplikacji Teams. 

### <a name="what-happens-if-a-store-manager-leaves-the-company"></a>Co się stanie, gdy kierownik sklepu opuści firmę?

Każdy, kto ma rolę właściciela, może dodać nowego kierownika sklepu w centrali Commerce i ponownie udostępnić zespoły, aby nowy menedżer miał niezbędne uprawnienia w usłudze Teams dla grupy. 

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie integracji Dynamics 365 Commerce i Microsoft Teams](commerce-teams-integration.md)

[Włączanie integracji Dynamics 365 Commerce i Microsoft Teams](enable-teams-integration.md)

[Obsługa Microsoft Teams z Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Synchronizowanie zarządzania zadaniami między punktami sprzedaży usług Microsoft Teams i Dynamics 365 Commerce POS](synchronize-tasks-teams-pos.md)

[Zarządzanie rolami użytkowników w usłudze Microsoft Teams](manage-user-roles-teams.md)

[Mapowanie sklepów i zespołów w przypadku, gdy istnieją już inne zespoły w usłudze Microsoft Teams](map-stores-existing-teams.md)
