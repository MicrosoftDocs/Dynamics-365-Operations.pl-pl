---
title: Tworzenie i wysyłanie przewodnika wdrażania do pracy poprzez Dynamics 365 for Talent - Onboard
description: W tym temacie wyjaśniono użycie Microsoft Dynamics 365 for Talent - Onboard do utworzenia szablonu dla przewodnika wdrażania do pracy dla nowych pracowników. To zadanie jest podstawowym pierwszym krokiem w zarządzaniu kapitałem ludzkim (HCM) zatrudniania do wycofania strategii.
author: andreabichsel
manager: ''
ms.date: 05/02/2019
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
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: de5d584e3b7edba2751aa0c83b0465df2c3e4f7d
ms.sourcegitcommit: 9f762fa89c5b432667aa156c22d679a7f601952d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/08/2019
ms.locfileid: "1731607"
---
# <a name="create-and-send-an-onboarding-guide-by-using-dynamics-365-for-talent-onboard"></a>Tworzenie i wysyłanie przewodnika wdrażania do pracy poprzez Dynamics 365 for Talent: Onboard

[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 for Talent: Onboard umożliwia tworzenie przewodników wdrażania do pracy z szablonów, które zostały utworzone samodzielnie, z szablonów, które są dostępne w galerii lub od podstaw.

Po utworzeniu przewodnika wdrażania do pracy można wysłać go do nowego pracownika. Alternatywnie można wysłać go do wielu nowych pracowników, których określisz w pliku Microsoft Excel, który można pobrać z aplikacji Onboard.

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-a-single-new-hire"></a>Utwórz przewodnik wdrażania do pracy z szablonu i wyślij go do jednego nowego pracownika

1. W menu po lewej stronie wybierz **Szablony**.
2. W obszarze **Moje szablony**, wybierz szablon, który chcesz skonfigurować jako przewodnik wdrażania do pracy dla nowego pracownika.
3. Edytuj szablon jak chcesz. Pamiętaj, aby regularnie zapisywać swoją pracę.
4. Po zakończeniu edytowania szablonu wybierz opcję **Utwórz przewodnik**.

    [![Utwórz przewodnik wdrażania do pracy z szablonu](./media/onboard-create-guide.png)](./media/onboard-create-guide.png)

5. W oknie **Utwórz Przewodnik**, w obszarze **Kogo wdrażasz do pracy**, wprowadź imię nowego pracownika lub adres e-mail. Jeśli nowy pracownik nie znajduje się jeszcze w systemie, wybierz pozycję **Dodaj** i wprowadź informacje o pracowniku.

    ![[Wprowadzanie informacji o przewodniku wdrażania do pracy](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

6. W obszarze **Kiedy zacznie się praca** wybierz datę początkową.
7. Jeśli przewodnik wdrażania do pracy powinien być automatycznie wysyłany do nowego pracownika w określonym dniu, upewnij się , że jest włączona opcja **Zaplanuj datę automatycznego wysyłania**, a następnie wybierz datę automatycznego wysyłania. Aby natychmiast wysłać przewodnik, wyłącz opcję **Zaplanuj datę automatycznego wysyłania**.
8. Wybierz opcję **Gotowe**.
9. Po zakończeniu edytowania przewodnika wdrażania do pracy wybierz pozycję **Wyślij** w prawym górnym rogu. Następnie wykonaj jeden z następujących kroków:

    - Aby wysłać nowemu pracownikowi łącze do przewodnika wdrażania do pracy, wybierz opcję **Kopiuj łącze**, a następnie wybierz **Kopiuj**.
    - Aby dostosować adres e-mail przewodnika wdrażania do pracy przed jego wysłaniem, wybierz pozycję **Dostosuj wiadomość e-mail przed wysłaniem**, wybierz pozycję **Dalej**, dostosuj żądany adres e-mail, a następnie wybierz pozycję **Wyślij**.
    - Aby wysłać wiadomość e-mail bez dostosowywania go, wybierz pozycję **Dalej**, a następnie wybierz pozycję **Wyślij**.

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-multiple-new-hires"></a>Utwórz przewodnik wdrażania do pracy z szablonu i wyślij go do wielu nowych pracowników.

Onboard pozwala wysłać przewodnik wdrażania do pracy do wielu nowych pracowników w tym samym czasie.

1. W menu po lewej stronie wybierz **Szablony**.
2. W obszarze **Moje szablony**, wybierz szablon, który chcesz skonfigurować jako przewodnik wdrażania do pracy dla nowych pracowników.
3. Edytuj szablon jak chcesz. Pamiętaj, aby regularnie zapisywać swoją pracę.
4. Po zakończeniu edytowania szablonu wybierz opcję **Utwórz przewodnik**.
5. W oknie **Utwórz przewodnik** zaznacz opcję **Musisz wdrożyć do pracy wiele osób jednocześnie**.

    [![Tworzenie przewodnika wdrażania do pracy dla wielu nowych pracowników](./media/onboard-send-guide-multiple-people.png)](./media/onboard-send-guide-multiple-people.png)

6. Wybierz **szablon nowego pracownika**.
7. Po pobraniu pliku xlsx wybierz opcję **Otwórz**, wprowadź informacje o pracownikach w skoroszycie programu Excel i zapisz skoroszyt.

    [![Pobieranie szablonu programu Excel do wysłania przewodnika po wielu nowych pracowników](./media/onboard-send-guide-download-spreadsheet.png)](./media/onboard-send-guide-download-spreadsheet.png)

    > [!NOTE]
    > Aby móc edytować skoroszyt, musisz wybrać opcję **Włącz edytowanie** w programie Excel.
    > 
    > [![Włączanie edytowania](./media/onboard-send-guide-enable-editing.png)](./media/onboard-send-guide-enable-editing.png)

8. Przeciągnij skoroszyt programu Excel do wyznaczonego obszaru w oknie **Tworzenie wielu przewodników** lub kliknij w dowolnym miejscu w tym obszarze, aby odszukać plik na komputerze.

    [![Przeciąganie edytowanego skoroszytu](./media/onboard-send-guide-drag-spreadsheet.png)](./media/onboard-send-guide-drag-spreadsheet.png)

9. Po zakończeniu edytowania przewodnika wdrażania do pracy wybierz pozycję **Wyślij** w prawym górnym rogu. Następnie wykonaj jeden z następujących kroków:

    - Aby wysłać nowemu pracownikowi łącze do przewodnika wdrażania do pracy, wybierz opcję **kopiuj łącze**, a następnie wybierz **Kopiuj**.
    - Aby dostosować adres e-mail przewodnika wdrażania do pracy przed jego wysłaniem, wybierz pozycję **Dostosuj wiadomość e-mail przed wysłaniem**, wybierz pozycję **Dalej**, dostosuj żądany adres e-mail, a następnie wybierz pozycję **Wyślij**.
    - Aby wysłać wiadomość e-mail bez dostosowywania go, wybierz pozycję **Dalej**, a następnie wybierz pozycję **Wyślij**.

## <a name="create-a-guide-without-using-a-template"></a>Utwórz przewodnik bez używania szablonu

Nie zawsze trzeba tworzyć przewodnik na podstawie szablonu. Jeśli wolisz, możesz utworzyć przewdonik od podstaw.

1. W menu po lewej wybierz opcję **Przewodniki**, a następnie wybierz przycisk **Dodaj** (znak plus \[**+**\]).
2. W oknie **Utwórz Przewodnik**, w obszarze **Kogo wdrażasz do pracy**, wprowadź imię nowego pracownika lub adres e-mail. Jeśli nowy pracownik nie znajduje się jeszcze w systemie, wybierz pozycję **Dodaj** i wprowadź informacje o pracowniku.

    ![[Wprowadzanie informacji o przewodniku wdrażania do pracy](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

3. W obszarze **Kiedy zacznie się praca** wybierz datę początkową.
4. Jeśli przewodnik wdrażania do pracy powinien być automatycznie wysyłany do nowego pracownika w określonym dniu, upewnij się , że jest włączona opcja **Zaplanuj datę automatycznego wysyłania**, a następnie wybierz datę automatycznego wysyłania. Aby natychmiast wysłać przewodnik, wyłącz opcję **Zaplanuj datę automatycznego wysyłania**.
5. Wybierz opcję **Gotowe**.

## <a name="save-a-guide-as-a-template"></a>Zapisz przewodnik jako szablon

Przewodnik wdrażania do pracy można zapisać jako szablon. W ten sposób można zaoszczędzić czas w przypadku konieczności późniejszego utworzenia kolejnych przewodników.

1. W menu po lewej stronie wybierz **Przewodniki**.
2. Wybierz przycisk **Więcej** (wielokropek \[**...**\]) dla przewodnika, na podstawie którego chcesz utworzyć szablon, a następnie wybierz opcję **Zapisz jako szablon**.

    ![[Zapisywanie przewodnika wdrażania do pracy jako szablon](./media/onboard-save-guide-as-template.png)](./media/onboard-save-guide-as-template.png)

3. W oknie **Zapisz jako nowy szablon** wprowadź nazwę nowego szablonu, a następnie wybierz opcję **Zapisz**.

## <a name="next-steps"></a>Następne kroki

- [Edytowanie przewodników i szablonów wdrażania do pracy](./onboard-edit-guides-templates.md)
- [Udostępnianie zawartości innym współautorom](./onboard-share-template.md)
- [Wyświetlanie stanu zadań i dołączania pracowników](./onboard-view-status.md)
- [Tworzenie zespołów rekrutacyjnych w Onboard](./onboard-create-team.md)

### <a name="see-also"></a>Informacje dodatkowe

- [Wypróbuj lub kup aplikację Onboard](https://dynamics.microsoft.com/talent/onboard/)
- [Co nowego](./whats-new.md)
- [Informacje o wersji](https://docs.microsoft.com/business-applications-release-notes/index)
- [Uzyskiwanie pomocy technicznej](./talent-support.md)
