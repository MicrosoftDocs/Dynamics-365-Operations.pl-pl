---
title: Tworzenie użytkowników Portalu klientów i zarządzanie nimi (zawiera wideo)
description: W tym artykule wyjaśniono, jak tworzyć konta użytkowników Portalu klienta i ustawiać dla nich uprawnienia.
author: Henrikan
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: ec4f20daac39e1728ab46db159059e51a0cae0a6
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103779"
---
# <a name="create-and-manage-customer-portal-users"></a>Tworzenie użytkowników Portalu klienta i zarządzanie nimi

[!include [banner](../includes/banner.md)]


Po wdrożeniu nie ma możliwości samodzielnej rejestracji użytkowników w witrynach utworzonych za pomocą Portalu klienta. Aby zalogować się i wykorzystać witrynę sieci Web, użytkownicy muszą zostać zaproszeni przez administratora. Firma Microsoft celowo zablokowała możliwość samodzielnej rejestracji dla użytkowników.

Aby użytkownik mógł skorzystać z witryny sieci Web, musi zostać utworzony rekord kontaktu dla tego użytkownika. Ten rekord wskazuje konto odbiorcy i firmę, do której należy użytkownik. Te informacje są istotne dla zapewnienia, że użytkownik może tworzyć i wyświetlać zamówienia sprzedaży.

Podczas samodzielnego rejestrowania użytkowników rekordy kontaktów są tworzone automatycznie. Dlatego nie można zagwarantować, że użytkownik wybierze odpowiednie konto klienta i firmę. Z drugiej strony proces zaproszenia umożliwia administratorowi przypisanie poprawnego konta klienta i firmy do rekordu kontaktu przed wysłaniem zaproszenia. Jeśli zastanawiasz się nad dostosowywaniem rozwiązania, aby użytkownicy mogli je zarejestrować samodzielnie, pamiętaj, aby wziąć pod uwagę ewentualne konsekwencje.

## <a name="video"></a>Wideo
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ADkI]

Film [Zaproś klientów do rejestracji i korzystania z Twojego portalu klienta](https://youtu.be/drGUYHX9QIQ) (widoczny powyżej) znajduje się na [liście odtwarzania aplikacji finansowych i operacyjnych](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) dostępnej w witrynie YouTube.

## <a name="prerequisite-setup"></a>Wymagania wstępne dotyczące konfiguracji

Kontakty w portalach Power Apps są przechowywane jako rekordy w tabeli **Kontakty** w Microsoft Dataverse. Podwójne zapisanie następnie synchronizuje te rekordy do Microsoft Dynamics 365 Supply Chain Management, jeśli jest to wymagane.

![Diagram systemu dla kontaktów Portalu klienta.](media/customer-portal-contacts.png "Diagram systemu dla kontaktów Portalu klienta")

Przed rozpoczęciem zapraszania nowych odbiorców należy się upewnić, że mapowanie tabeli **Kontaktów** zostało włączone w trybie podwójnego zapisywania.

## <a name="the-invitation-process"></a>Proces zaproszenia

Aby zaprosić istniejący kontakt do portalu klienta, należy wykonać kroki w [Zaproś kontakty do swoich portali](/powerapps/maker/portals/configure/invite-contacts) w dokumentacji portali Power Apps.

Przed zaproszeniem klienta o dołączenie do portalu klienta należy się upewnić, że [rekord kontaktu](/powerapps/maker/portals/configure/configure-contacts) jest dostępny i skonfigurowany w następujący sposób:

1. Ustaw pole **Firma** na firmę, do której ma należeć klient w Supply Chain Management.
2. Ustaw pole **Numer konta** na numer konta klienta, który ma posiadać klient w Supply Chain Management.

Po utworzeniu kontaktu należy go wyświetlić w Supply Chain Management.

Aby uzyskać więcej informacji, przejrzyj informacje [Konfigurowanie kontaktu do użycia w portalu](/powerapps/maker/portals/configure/configure-contacts) w dokumentacji portali Power Apps.

## <a name="out-of-box-web-roles-and-table-permissions"></a>Uprawnienia ról i tabel internetowych gotowe do użycia

Role użytkowników w portalach Power Apps są definiowane przez [role internetowe](/powerapps/maker/portals/configure/create-web-roles) i [uprawnienia tabeli](/powerapps/maker/portals/configure/assign-entity-permissions). Kilka ról jest zdefiniowanych dla portalu klienta od razu. Można tworzyć nowe role, a także modyfikować i usuwać istniejące role.

### <a name="out-of-box-web-roles"></a>Gotowe do użycia role sieci Web

W tej sekcji opisano role sieci Web dostarczane z portalem klienta.

Aby uzyskać więcej informacji na temat modyfikowania nieużywanych ról użytkowników, odwiedź witrynę [Tworzenie ról w sieci Web dla portali](/powerapps/maker/portals/configure/create-web-roles) i [Dodaj zabezpieczenia oparte na rekordach, korzystając z uprawnień tabeli dla portali](/powerapps/maker/portals/configure/assign-entity-permissions) w dokumentacji portali Power Apps.

#### <a name="administrator"></a>Administrator

Administrator nadzoruje i utrzymuje witrynę. Osoba ta przygotuje i skonfiguruje portal klienta. Administrator utrzymuje aspekty IT i bezpieczeństwa portalu i zapewnia, że wszystko działa płynnie. Administrator może również dostosować i/lub zmienić portal, dodając nowe funkcje, tworząc nowe role i wykonując inne zadania.

#### <a name="customer-representative"></a>Przedstawiciel klienta

Przedstawiciel klienta pracuje dla firmy klienta i jest odpowiedzialny za zarządzanie zamówieniami, które składa firma. Przedstawiciel klienta może zobaczyć wszystkie zamówienia, które zostały umieszczone dla firmy oraz użytkowników, którzy je złożyli. Ponadto przedstawiciel klienta może przeglądać informacje ogólne dotyczące konta i kontakty, które mogą składać zamówienia w imieniu tego konta.

#### <a name="authorized-users"></a>Autoryzowani użytkownicy

Autoryzowani użytkownicy mogą składać zamówienia i wyświetlać stan złożonych zamówień. Nie mogą jednak wyświetlać stanu zamówień, które zostały złożone przez innych użytkowników należących do firmy.

#### <a name="unauthorized-users"></a>Autoryzowani użytkownicy

Nieuprawnieni użytkownicy nie mogą wyświetlać żadnych danych. Mogą one wyświetlać tylko informacje publiczne, takie jak warunki i zasady, oraz szczegóły dotyczące firmy, w której jest uruchomiony Portal klienta.

#### <a name="example"></a>Przykład

W poniższej tabeli przedstawiono zamówienia sprzedaży, które użytkownicy należący do poszczególnych ról sieci Web mogą zobaczyć w systemie.

| Zamówienie sprzedaży | Administrator | Przedstawiciel klienta dla klienta&nbsp;X | Autoryzowany użytkownik: Jane | Autoryzowany użytkownik: Sam | Autoryzowany użytkownik: May |
|---|---|---|---|---|---|
| Klient&nbsp;X Zamawiający:&nbsp;Jane | Tak | Tak | Tak | Nie | Nie |
| Klient&nbsp;X Zamawiający:&nbsp;Sam | Tak | Tak | Nie | Tak | Nie |
| Klient&nbsp;Y Zamawiający:&nbsp;May | Tak | Nie | Nie | Nie | Nie |

> [!NOTE]
> Mimo że zarówno Sam, jak i Jane są kontaktami pracującymi dla klienta X, widzą tylko złożone przez siebie zamówienia i nic więcej. Chociaż May ma zamówienie w systemie, nie widzi tego zamówienia w portalu klienta, ponieważ jest nieautoryzowanym użytkownikiem. (Dodatkowo musiała złożyć zamówienie za pośrednictwem innego kanału niż portal klienta).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
