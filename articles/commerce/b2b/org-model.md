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
ms.openlocfilehash: 450efd595a1cc1b72b2e62afbdd4518bcca59cb0
ms.sourcegitcommit: f9df202aefef761be52c0360b0e22da88773914c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035950"
---
# <a name="create-org-modeling-hierarchies-for-b2b-organizations"></a>Tworzenie hierarchii modelowania organizacji dla organizacji B2B

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób tworzenia hierarchii modelowania organizacyjnego dla organizacji typu B2B (business-to-business) w Microsoft Dynamics 365 Commerce.

W centrali Commerce organizacje partnerów biznesowych są reprezentowane przez jednostki hierarchii klientów i odbiorców. Organizacja partnera biznesowego i jej użytkownicy są reprezentowani jako klienci, a hierarchie klientów służą do kojarzenia tych klientów ze sobą.

Gdy prośba partnera biznesowego o dołączenie do witryny handlu elektronicznego B2B zostanie zatwierdzona, wykonywane są następujące czynności:

- Ponadto w systemie są tworzone dwa nowe rekordy odbiorcy: rekord odbiorcy organizacji **Typu organizacji** partnera biznesowego i rekord klienta **typu Osoba** dla zleceniodawcy (to znaczy użytkownika partnera biznesowego, który przesłał żądanie).
- Nowy rekord hierarchii odbiorcy jest tworzony w **Odbiorca \> Hierarchia odbiorców**. Ten rekord ma następujące właściwości nagłówka:

    - **Identyfikator hierarchii odbiorcy** – unikatowy identyfikator hierarchii odbiorcy. Ten identyfikator używa sekwencji numerów zdefiniowanej w parametrach współdzielonych aplikacji Commerce w Commerce headquarters.
    - **Nazwa** — nazwa organizacji partnera biznesowego, określona w żądaniu przysyłania.
    - **Cel** — właściwość jest ustawiona na wstępnie zdefiniowaną wartość **organizacji B2B**.
    - **Organizacja** — Identyfikator klienta partnera biznesowego.

Oto szczegóły rekordu hierarchii odbiorcy:

- Rekord odbiorcy dla żądacy jest skojarzony z hierarchią odbiorcy.
- Rola administratora jest skojarzona z żądaniem.

Gdy administrator dodaje więcej użytkowników do organizacji partnera biznesowego w witrynie B2B, w programie Commerce Headquarters jest tworzony nowy rekord odbiorcy dla każdego użytkownika. Ten rekord odbiorcy jest również dodawany do odpowiedniego rekordu hierarchii odbiorcy dla partnera biznesowego i ma rolę „użytkownika”

> [!NOTE]
> W większości przypadków odpowiednie wartości właściwości wszystkich rekordów klientów w hierarchii powinny być zgodne. Na przykład, ponieważ wszyscy użytkownicy partnerów biznesowych powinni otrzymywać podobne ceny produktów, ich grupy cenowe i powiązane konfiguracje powinny być zgodne. Jednak system nie wymusza tej spójności. W związku z tym odpowiedni użytkownicy Commerce headquarters są odpowiedzialni za zapewnienie, że wartości właściwości i konfiguracje są zgodne dla wszystkich klientów w danej hierarchii.

Użytkownicy Commerce Headquarters mogą przeglądać wartości właściwości dla wszystkich rekordów klientów w hierarchii w widoku obok siebie. Wybierz odpowiednie właściwości rekordu odbiorcy, wybierając nazwy kart z menu rozwijanego. Użytkownicy mogą bezpośrednio wyświetlać i edytować wartości właściwości z tego widoku. Alternatywnie, jeśli chcesz zastosować wszystkie wartości z rekordu klienta administratora do wszystkich rekordów klientów użytkownika, wybierz opcję **Zastąp** w szczegółach hierarchii klientów.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie witryny handlu elektornicznego B2B](set-up-b2b-site.md)

[Zarządzaj użytkownikami partnerów biznesowych w witrynach handlu elektronicznego B2B](manage-b2b-users.md)

[Konfigurowanie metody płatności na konto odbiorcy dla witryn handlu elektronicznego B2B](payment-method.md)

[Ustawianie limitów ilości produktów dla witryn B2B handlu elektronicznego](quantity-limits.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]