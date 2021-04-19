---
title: Dostosowywanie i korzystanie z Portalu klienta
description: W tym temacie opisano sposób dostosowania Portalu klienta po dodaniu go do systemu.
author: dasani-madipalli
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 16d5c13c0fbff8c5033b0d1e9dd0d07851521126
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840780"
---
# <a name="customize-and-use-the-customer-portal"></a>Dostosowywanie i korzystanie z Portalu klienta

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano różne strony dostępne do użytku w Portalu klienta. Wyjaśnia, co robią strony i w jaki sposób można je dostosować.

W Portalu klienta jest dostępnych kilka stron sieci Web i akcji, które są dostępne do użytku od razu. Następująca mapa witryny umożliwia przegląd tych stron sieci Web i akcji oraz ról, które mogą wykonywać te akcje.

![Mapa witryny Portalu klienta](media/customer-portal-site-map.png "Mapa witryny Portalu klienta")

## <a name="typical-customizations"></a>Standardowe dostosowania

Poniższe tematy umożliwiają zapoznanie się z podstawowymi portalami Power Apps i sposobami dostosowywania portali:

- [Praca z szablonami](https://docs.microsoft.com/powerapps/maker/portals/work-with-templates) — ten temat zawiera ogólne omówienie działania portali Power Apps oraz proste dostosowania portali.
- [Zarządzanie zawartością portalu](https://docs.microsoft.com/dynamics365/portals/manage-portal-content) — w tym temacie wyjaśniono, jak można zarządzać i dostosowywać zawartość obszaru w portalu.
- [Edycja CSS](https://docs.microsoft.com/powerapps/maker/portals/edit-css) — ten temat pomaga wprowadzać bardziej złożone dostosowania do interfejsu użytkownika (UI) portalu.
- [Utwórz motyw dla swojego portalu](https://docs.microsoft.com/dynamics365/portals/create-theme) – w tym temacie opisano sposób tworzenia motywu interfejsu użytkownika portalu.
- [Tworzenie i uwidacznianie zawartości portalu w prosty sposób](https://docs.microsoft.com/dynamics365/portals/create-expose-portal-content) — ten temat pomaga w zarządzaniu danymi i tabelami używanymi w portalu.
- [Konfigurowanie kontaktu do użycia w portalu](https://docs.microsoft.com/powerapps/maker/portals/configure/configure-contacts) — w tym temacie opisano sposób tworzenia i dostosowywania ról użytkowników oraz sposobu działania zabezpieczeń i uwierzytelniania w portalach Power Apps.
- [Konfigurowanie notatek dla formularzy tabel i formularzy internetowych w portalach](https://docs.microsoft.com/powerapps/maker/portals/configure-notes) — w tym temacie opisano sposób dodawania dokumentów i dodatkowego magazynu do portalu.
- [Obsługa błędów w witrynie sieci Web portalu](https://docs.microsoft.com/powerapps/maker/portals/admin/view-portal-error-log) — w tym temacie opisano sposób wyświetlania dzienników błędów portalu i przechowywania ich na koncie magazynu obiektów BLOB Microsoft Azure.

## <a name="customize-the-order-creation-process"></a>Dostosowywanie procesu tworzenia zamówień

Jeśli użytkownik prześle zamówienie za pomocą portalu klienta, zamówienie jest automatycznie synchronizowane z odpowiednim środowiskiem Dynamics 365 Supply Chain Management. Ponieważ użytkownik jest klientem zewnętrznym, niektóre wymagane informacje są celowo ukryte. Te informacje będą automatycznie wypełniane po przesłaniu formularza.

W tej sekcji przedstawiono sposób konfigurowania kontaktów w celu uniknięcia błędów. Opisuje ona pola, które są automatycznie ustawiane i w jaki sposób można zmodyfikować wartość tych pól.

### <a name="the-out-of-box-order-creation-process"></a>Gotowy do użycia proces tworzenia zamówień

Poniżej przedstawiono standardowe etapy składania zamówienia z poziomu portalu klienta.

1. Na stronie głównej zaznacz kafelek **Utwórz zamówienie**, aby otworzyć kreatora **Utwórz zamówienie**.
1. Na stronie **Informacje o zamówieniu** ustaw następujące pola:

    - **Żądana data odbioru** — umożliwia określenie daty dostawy.
    - **Adres dostawy** — umożliwia wprowadzenie adresu, na który ma zostać dostarczone zamówienie.
    - **Firma** — umożliwia wybór nazwy firmy odbiorcy. To pole jest ustawiane automatycznie dla użytkowników niebędących administratorami.
    - **Numer zapotrzebowania** — umożliwia wprowadzenie numeru zapotrzebowania dla zamówienia. Pole to nie jest wymagane.
    - **Kraj/region wysyłki** — umożliwia wprowadzenie kraju lub regionu, do którego zostaną dostarczone towary. To pole jest ustawiane automatycznie dla użytkowników niebędących administratorami.

    ![Strona informacji zamówienia](media/customer-portal-order-information.png "Strona informacji zamówienia")

1. Wybierz pozycję **Następny**.
1. Na stronie **Elementy** wybierz przycisk **Dodaj pozycję**.

    ![Strona pozycji](media/customer-portal-items.png "Strona pozycji")

1. W oknie dialogowym **Informacje o pozycji** można ustawić następujące pola:

    - **Nazwa produktu** — umożliwia wyszukanie i wybranie produktu, który ma zostać dodany do zamówienia.
    - **Ilość** — umożliwia wprowadzenie ilości wybranego produktu.
    - **Jednostka** — umożliwia określenie jednostka miary (na przykład **szt.**, **kg** lub **pudełko**).
    - **Szacowana kwota netto** — wartość jest obliczana jako Szacowana cena towaru x ilość dla wybranej jednostki.

    ![Okno dialogowe Informacje o pozycji](media/customer-portal-item-information.png "Okno dialogowe Informacje o pozycji")

1. Wybierz **Prześlij**, aby dodać towar do zamówienia.
1. Powtarzaj kroki od 4 do 6, dopóki nie dodasz wszystkich towarów, które chcesz zamówić.
1. Po zakończeniu dodawania towarów wybierz przycisk **Dalej** na stronie **Pozycje**.
1. Strona **Informacje o zamówieniu** zawiera podsumowanie tego zamówienia. Przejrzyj zawartość zamówienia i szczegóły dotyczące dostawy. Jeśli wszystko wygląda poprawnie, wybierz opcję **Prześlij**, aby przesłać zamówienie.

    ![Strona informacji zamówienia](media/customer-portal-order-submit.png "Strona informacji zamówienia")

### <a name="standard-data-setup"></a>Standardowe dane konfiguracji

Aby zapewnić płynne działanie użytkownika, Portal klienta automatycznie wprowadza wartości dla kilku wymaganych pól. Te wartości są oparte na informacjach z rekordu kontaktu odbiorcy, który przesyła zamówienie.

Dla każdego [wiersza kontaktu](https://docs.microsoft.com/powerapps/maker/portals/configure/configure-contacts) należącego do odbiorcy, który będzie używał portalu klienta do przesyłania zamówień, należy określić wartości dla następujących wymaganych pól. W przeciwnym razie pojawią się błędy.

- **Firma** – Wybierz firmę, do której należy zamówienie.
- **Potencjalny klient** – Konto odbiorcy skojarzone z zamówieniem magazynowym
- **Cennik** — niestandardowy Cennik dla odbiorcy
- **Waluta** — Waluta ceny
- **Kraj/region wysyłki** — Umożliwia wprowadzenie kraju lub regionu, do którego zostaną dostarczone towary

Dla tabeli zamówienia sprzedaży automatycznie ustawiane są następujące pola:

- **Język** — Język zamówienia (domyślnie jest pobierana wartość z rekordu kontaktu)
- **Kraj/region dostawy** — kraj lub region, do którego są dostarczane towary (wartość domyślna jest pobierana z rekordu kontaktu)
- **Osoba kontaktowa** — użytkownik, z którym można się skontaktować w celu uzyskania informacji o zamówieniu (wartość domyślna jest pobierana z rekordu kontaktu)
- **Firma** — firma, do której należy zamówienie (domyślnie jest ona pobierana z rekordu kontaktu)
- **Potencjalny klient** — konto odbiorcy skojarzone z zamówieniem (wartość domyślna jest pobierana z rekordu kontaktu)
- **Fakturowanie odbiorcy** — Konto rozliczeniowe zamówienia (wartością domyślną jest potencjalny klient z rekordu kontaktu)
- **Nazwa zamówienia sprzedaży** — Nazwa zamówienia sprzedaży (wartość domyślna to **Zamówienie sprzedaży**)
- **Waluta** — Waluta ceny (domyślnie wartość jest pobierana z rekordu kontaktu)
- **Cennik** — niestandardowy Cennik dla odbiorcy (Domyślnie wartość jest pobierana z rekordu kontaktu)
- **Opis adresu dostawy** — adres dostawy zamówienia sprzedaży (wartość domyślna to **opis adresu dostawy**)

### <a name="modify-the-order-creation-process"></a>Modyfikacja procesu tworzenia zamówień

Można dowolnie modyfikować wygląd i interfejs użytkownika portalu odbiorcy, jeśli nie zmieni się podstawowego procesu tworzenia zamówienia. Aby zmienić proces tworzenia zamówienia, należy pamiętać o kilku punktach.

Nie należy usuwać następujących kolumn z tabeli zamówienia sprzedaży w Microsoft Dataverse, ponieważ są one wymagane do utworzenia zamówienia sprzedaży w trybie podwójnych odpisów:

- **Firma** – Wybierz firmę, do której należy zamówienie.
- **Nazwa** — Nazwa zamówienia sprzedaży
- **Waluta** — Waluta ceny
- **Cennik** — niestandardowy Cennik dla odbiorcy
- **Kraj/region wysyłki** — Umożliwia wprowadzenie kraju lub regionu, do którego zostaną dostarczone towary
- **Potencjalny klient** – Konto odbiorcy skojarzone z zamówieniem magazynowym
- **Język** — Język zamówienia (zazwyczaj jest to język potencjalnego odbiorcy)
- **Opis adresu dostawy** — adres dostawy zamówienia sprzedaży

W przypadku towarów wymagane są następujące kolumny:

- **Produkt** — produkt do zamówienia
- **Ilość** — Ilość wybranego produktu
- **Jednostka** — Jednostka miary (na przykład **szt.**, **kg** lub **pudełko**)
- **Kraj/region wysyłki** — kraj lub region dostawy
- **Opis adresu dostawy** — adres dostawy zamówienia

Należy upewnić się, że portal odbiorcy w jakiś sposób przesyła wartości dla wszystkich tych kolumn.

Jeśli chcesz dodać kolumny do strony lub usunąć kolumny, zapoznaj się z tematem [Twórz lub edytuj szybkie formularze, aby usprawnić wprowadzanie danych](https://docs.microsoft.com/dynamics365/customerengagement/on-premises/customize/create-edit-quick-create-forms).

Aby zmienić ustawienia i sposób ustawiania wartości kolumn podczas zapisywania strony, należy zapoznać się z poniższymi informacjami w dokumentacji portali Power Apps:

- [Wstępnie wypełnione pole](https://docs.microsoft.com/powerapps/maker/portals/configure/configure-web-form-metadata#prepopulate-field)
- [Ustawienie wartości przy zapisywaniu](https://docs.microsoft.com/powerapps/maker/portals/configure/configure-web-form-metadata#set-value-on-save)

## <a name="customize-the-home-page"></a>Dostosowanie strony głównej

Wszystkie formanty w portalu klienta są wbudowanymi kontrolkami portali Power Apps. Można je dostosować, wykonując kroki w formularzu [Redagowanie strony](https://docs.microsoft.com/powerapps/maker/portals/compose-page)w dokumentacji portali Power Apps.

Tylko formant niestandardowy uwzględniony w szablonie portalu klienta jest używany do tworzenia tabliczek na stronie głównej.

![Kafelki na strony głównej](media/customer-portal-home-page-tiles.png "Kafelki na strony głównej")

Aby zmodyfikować kafelki, należy wykonać następujące czynności.

1. Otwórz [aplikację Zarządzanie portalem](https://docs.microsoft.com/powerapps/maker/portals/configure/configure-portal).
1. W okienku nawigacji po lewej stronie zaznacz **Szablony strony**.

    ![Okienko nawigacji zarządzania portalami](media/customer-portal-nav.png "Okienko nawigacji zarządzania portalami")

1. Wybierz szablon strony o nazwie **Strona główna**.
1. W polu **Szablon sieci Web** wybierz łącze **Strona główna**, aby otworzyć kod źródłowy tej strony.

    ![Pole szablonu sieci Web](media/customer-portal-web-template.png "Pole szablonu sieci Web")

1. Teraz widzisz wszystkie kody źródłowe strony głównej i możesz je zmodyfikować, jeśli jest to wymagane.

## <a name="resources"></a>Zasoby

Więcej informacji na temat konfigurowania i dostosowywania portalu klienta można znaleźć w następujących zasobach:

- [Dokumentacja portali Power Apps](https://docs.microsoft.com/powerapps/maker/portals/overview)
- [Dokumentacja podwójnego zapisu](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)
- [Cykl życia portalu — informacje](https://docs.microsoft.com/powerapps/maker/portals/admin/portal-lifecycle)
- [Uaktualnianie portalu](https://docs.microsoft.com/powerapps/maker/portals/admin/upgrade-portal)
- [Migruj konfigurację portalu](https://docs.microsoft.com/powerapps/maker/portals/admin/migrate-portal-configuration)
- [Zarządzanie cyklem życia rozwiązania: Dynamics 365 dla aplikacji Customer Engagement](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]