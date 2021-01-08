---
title: Edytowanie przewodników wdrażania do pracy i szablonów w Dynamics 365 Talent - Onboard
description: W tym temacie opisano sposób dodawania działań i innych informacji do przewodników wdrażania do pracy i szablonów w Dynamics 365 Talent - Onboard rozwiązania Microsoft.
author: andreabichsel
manager: ''
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-06-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 291f7aefac61c26dfab81cfff28c1c6580d46de5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462250"
---
# <a name="edit-onboarding-guides-and-templates"></a>Edytowanie przewodników i szablonów wdrażania do pracy

[!include [banner](includes/banner.md)]

Po utworzeniu przewodnika lub szablonu w systemie Microsoft Dynamics 365 Talent: Onboard należy dodać do niego wprowadzenie, działania, kontakty i zasoby. Onboard umożliwia dołączanie bogatej zawartości do przewdoników wdrażania do pracy, w tym:

- Filmiki YouTube
- Prezentacje aplikacji Microsoft Sway
- Aplikacje Microsoft PowerApps
- Filmiki Microsoft Stream
- Formularze Microsoft Forms
- Ramki iframe, które zawierają zawartość sieci Web

## <a name="edit-introductions-or-activities-imported-from-a-template"></a>Umożliwia edytowanie wstępów i działań zaimportowanych z szablonu

W przypadku utworzenia przewodnika wdrażania do pracy na podstawie szablonu lub zaimportowaniu działań z jednego szablonu do innego zostanie wyświetlony przycisk **Zablokuj** w zaimportowanych działaniach. Są to tzw. *działania zarządzane*.

[![Zarządzane działania](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)

Po wybraniu zarządzanego działania można wyświetlić szablon źródłowy u góry działania.

[![Źródło zarządzanego działania](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)

Jeśli użytkownik edytuje działanie w szablonie, Onboard przekaże zmiany do wszystkich szablonów i niewysłanych przewodników opartych na tym szablonie. Jeśli wybierzesz niewysłany przewodnik na podstawie edytowanego szablonu, a następnie wybierzesz kartę **Działania** w przewodniku, zobaczysz informację, że poradnik został zmieniony. Aby anulować powiadomienie, należy wybrać **OK**. 

[![Zmień powiadomienie](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)

Obok zaktualizowanych działań zostanie wyświetlona czarna kropka.

[![Zmienione działanie](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)

Nie można edytować działań zarządzanych poza oryginalnym szablonem, z wyjątkiem dodawania osoby przydzielonej, terminu lub innych informacji w prawej sekcji działania.

Jeśli chcesz edytować zarządzane działanie lub jeśli nie chcesz, aby dana czynność otrzymywała aktualizacje z szablonu, z którego pochodzi, wybierz przycisk **Zablokuj** dla tego działania. Przycisk **Zablokuj** zniknie. Działanie nie będzie już zarządzane przez oryginalny szablon i nie będzie już otrzymywać aktualizacji z tego szablonu. Aktualizacje wprowadzane do działania nie mają wpływu na oryginalny szablon.

W przypadku usunięcia działania z przewodnika i wprowadzenia zmian z szablonu tego przewodnika działanie pozostanie usunięte w przewodniku.

> [!NOTE]
> W szablonach nie są zarządzane kontakty i zasoby. Ponadto sekcje nie są zarządzane, więc w przypadku dodania lub edycji sekcji w szablonie zmiany nie zostaną przesunięte do żadnych przewodników lub szablonów używających tego szablonu.
> 
> W przypadku dodania nowych działań do szablonu nowe działania są przekazywane do przewodników i szablonów opartych na tym szablonie, a nowe działania są wyświetlane u góry.

## <a name="import-activities-from-another-template"></a>Importowanie działań z innego szablonu

Istnieje możliwość importowania działań z jednego lub większej liczby szablonów do przewodnika lub szablonu.

1. Wybierz przewodnik lub szablon, który ma zostać edytowany.

2. Kliknij kartę **Działania**.

3. Wybierz kartę **Import** w sekcji po prawej stronie.

   [![Importowanie działań](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)

4. Aby wyświetlić podgląd zadań na nowej karcie w przeglądarce, wybierz przycisk **Otwórz w nowej karcie** na dowolnym szablonie.

   [![Importowanie działań](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)

5. Przeciągnij i upuść żądany szablon do miejsca w szablonie przewodnika, gdzie mają się pojawiać działania. Kontynuuj edytowanie przewodnika lub szablonu

Zaimportowane działania będą zawierać przycisk **Zablokuj**, który wskazuje działania zarządzane przez szablon, z którego zaimportowano dane. Po wprowadzeniu zmian w zaimportowanym szablonie działania te będą aktualizowane w szablonie, do którego zostały zaimportowane. Jednak zmiany nie będą automatycznie przekazywane do żadnych prowadnic utworzonych na podstawie zaimportowanego szablonu.

## <a name="push-changes-from-a-template-to-other-templates-or-guides"></a>Wypchnij zmiany z szablonu do innych szablonów lub przewodników

W przypadku edytowania szablonu zawierającego działania używane w innych szablonach lub przewodnikach należy wprowadzić zmiany, jeśli mają być wyświetlane w innych szablonach lub przewodnikach.

Jeśli nie masz pewności, czy działania szablonu są używane w innych szablonach lub w przewodnikach, wybierz opcję **Używane** na karcie, aby zobaczyć, gdzie są wyświetlane te działania.

   [![Zobacz przewodniki i szablony, w których są używane działania](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)

Aby wprowadzić zmiany:

1. Aby zapisać zmiany, należy zaznaczyć przycisk **Zapisz**. W przeciwnym razie zostanie wyświetlony monit o zapisanie zmian w następnym kroku.

2. Wybierz **Wyślij te zmiany**.

   
## <a name="add-or-edit-an-introduction"></a>Dodawanie lub edytowanie wprowadzenia

1. Na karcie **Wprowadzenie** wprowadź tytuł przewodnika i komunikat otwierający. Aby skorzystać z przykładowego tekstu, wybierz opcję **Używaj tego komunikatu**.

    [![Karta wprowadzenie w szablonie Onboard](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)

2. Użyj przycisków formatowania, aby wywoływać tekst w razie konieczności lub dodać obrazy lub łącza.
3. Wybierz **Zapisz**, żeby zapisać pracę.

## <a name="add-or-edit-activities"></a>Dodaj lub edytuj działania

1. Na karcie **Działania** przeciągnij elementy z prawej strony do obszaru edycji.
2. Aby zorganizować przewodnik w sekcjach, przeciągnij element **Nowa sekcja** do obszaru edycji, a następnie wprowadź nazwę i opcjonalny opis sekcji.

    ![[Dodawanie nowej sekcji do przewodnika lub szablonu wdrażania do pracy](./media/onboard-edit-add-section.png)](./media/onboard-edit-add-section.png)

3. Aby dodać działania dotyczące nowego zatrudnienia, przeciągnij element **Nowe działanie** do obszaru edycji, a następnie wprowadź nazwę i opis działania.

    ![[Dodawanie nowego działania do przewodnika lub szablonu wdrażania do pracy](./media/onboard-edit-add-activity.png)](./media/onboard-edit-add-activity.png)

4. Dodaj zawartość sformatowaną do przewodnika wdrażania do pracy:

    - Aby dodać filmik YouTube, przeciągnij element **YouTube** do obszaru edycji, wprowadź nazwę i opis działania, a następnie wprowadź adres URL wideo YouTube.
    - Aby dodać prezentację lub biuletyn w aplikacji Sway, przeciągnij element **Sway** do obszaru edycji, wprowadź nazwę i opis działania, a następnie wprowadź osadzony adres URL prezentacji lub biuletynu dla aplikacji Sway.
    - Aby dodać aplikację Microsoft Power Apps, przeciągnij element **Power Apps** do obszaru edycji, wprowadź nazwę i opis działania, a następnie wybierz aplikację Power Apps lub wprowadź identyfikator aplikacji Power Apps.
    - Aby dodać filmik Microsoft Stream, przeciągnij element **Microsoft Stream** do obszaru edycji, wprowadź nazwę i opis działania, a następnie wprowadź adres URL wideo Microsoft Stream.
    - Aby dodać formularz programu Microsoft Forms, przeciągnij element programu **Microsoft Forms** do obszaru edycji, wprowadź nazwę i opis działania, wprowadź adres URL formularza Microsoft Forms i określ rozmiar obszaru ekranu.
    - Aby dodać iframe zawierające treści internetowe, przeciągnij element programu **Treści internetowe (iframe)** do obszaru edycji, wprowadź nazwę i opis działania, wprowadź adres URL i treść oraz określ rozmiar obszaru ekranu.

    ![[Dodawanie zawartości sformatowanej do przewodnika lub szablonu wdrażania do pracy](./media/onboard-edit-add-rich-content.png)](./media/onboard-edit-add-rich-content.png)

2. Opcjonalnie: w obszarze po prawej stronie każdego działania należy przypisać działanie do określonej osoby lub roli, dodać termin płatności i osobę kontaktową, a następnie przypisać kolor kategorii. Podczas przypisywania działania do osoby lub roli tworzone jest zadanie dla każdej jednostki. To zadanie pojawia się w menu **Zadania** w Onboard.

    [![Przypisywanie działania do przewodnika lub szablonu wdrażania do pracy](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)

3. Wybierz **Zapisz**, żeby zapisać pracę.

Aby usunąć działanie lub sekcję, wybierz przycisk **Usuń** (symbol kosza) znajdujący się w prawym górnym rogu działania lub sekcji.

Aby zmienić kolejność działań i sekcji, przeciągnij je do nowej lokalizacji.

## <a name="add-or-edit-contacts"></a>Dodaj lub edytuj kontakty

Możesz dodać osoby kontaktowe, które mogą pomóc w nowym zatrudnieniu pomyślne od pierwszego dnia. Tymi kontaktami mogą być rekruterzy, członkowie zespołu, znajomi wdrażania do pracy, doradcy, Administratorzy oraz personel pomocy technicznej działu informatycznego.

1. Na karcie **Kontakty** wybierz opcję **Nowy kontakt**.
2. W oknie dialogowym **Dodawanie członka zespołu** wprowadź imię i nazwisko osoby kontaktowej lub adres e-mail, a następnie wprowadź krótki opis wyjaśniający, w jaki sposób osoba kontaktowa może pomóc nowym zatrudnieniu, a następnie wybierz opcję **Dodaj**. 

    ![[Dodawanie kontaktów do przewodnika lub szablonu wdrażania do pracy](./media/onboard-edit-add-contact.png)](./media/onboard-edit-add-contact.png)

    Alternatywnie można wybrać co najmniej jeden kontakt w ramach **Sugestie**.

3. Wybierz **Zapisz**, żeby zapisać pracę.

Aby usunąć kontakt, wybierz przycisk **Usuń** (kosz na śmieci) z prawej strony kontaktu.

Aby edytować kontakt, wybierz przycisk **Edytuj** (symbol ołówka) z prawej strony kontaktu.

## <a name="add-or-edit-resources"></a>Dodaj lub edytuj zasoby

Można dodawać przydatne pliki, mapy i łącza do sekcji **Zasoby** w przewodniku wdrażania do pracy.

1. Na karcie **Zasoby** wybierz opcję **Nowe zasoby**.
2. Wykonaj jeden z następujących kroków:

    - Aby dodać plik, wybierz kartę **Plik** i przeciągnij plik do wyznaczonego obszaru. (Można również kliknąć w dowolnym miejscu w tym obszarze, aby odszukać plik na komputerze lub wybrać **Przeglądaj OneDrive**.) Wprowadź nazwę pliku, a następnie wybierz przycisk **Dodaj**.
    - Aby dodać łącze, wybierz kartę **Łącze**, wprowadź nazwę i adres łącza, a następnie wybierz opcję **Dodaj**.
    - Aby dodać mapę, wybierz kartę **Mapa**, wprowadź nazwę i adres mapy, a następnie wybierz opcję **Dodaj**. Onboard będzie uwzględniał Mapę określonego adresu.

    ![[Dodawanie zasobu do przewodnika lub szablonu wdrażania do pracy](./media/onboard-edit-add-resource.png)](./media/onboard-edit-add-resource.png)

3. Wybierz **Zapisz**, żeby zapisać pracę.

Aby usunąć zasoby, wybierz przycisk **Usuń** (kosz na śmieci) z prawej strony zasobu.

Aby edytować kontakt, wybierz przycisk **Edytuj** (symbol ołówka) z prawej strony zasobu.

## <a name="next-steps"></a>Następne kroki

- [Udostępnianie zawartości innym współautorom](./onboard-share-template.md)
- [Wyświetlanie stanu zadań i dołączania pracowników](./onboard-view-status.md)
- [Tworzenie zespołów rekrutacyjnych w Onboard](./onboard-create-team.md)

### <a name="see-also"></a>Informacje dodatkowe

- [Wypróbuj lub kup aplikację Onboard](https://dynamics.microsoft.com/talent/onboard/)
- [Nowości i zmiany w Dynamics 365 Talent](./whats-new.md)
- [Plany wydań](https://docs.microsoft.com/business-applications-release-notes/index)
- [Uzyskiwanie pomocy technicznej dotyczącej rozwiązania Microsoft Dynamics 365 Talent](./talent-support.md)
