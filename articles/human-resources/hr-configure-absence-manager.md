---
title: Konfigurowanie roli menedżera nieobecności
description: W tym temacie wyjaśniono, jak skonfigurować rolę menedżera nieobecności do zarządzania urlopami pracowniczymi.
author: hasrivas
ms.date: 07/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace, LeaveAbsenceManager
audience: Application User
ms.search.scope: Human Resources
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: hasrivas
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e8a8250b36d2774ac308637253b780592df316cd
ms.sourcegitcommit: 86d38cf57abe768e5bccde48b28280bc2224080c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2021
ms.locfileid: "6639613"
---
# <a name="configure-the-absence-manager-role"></a>Konfigurowanie roli menedżera nieobecności

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

W niektórych organizacjach menedżerowie osób mogą nie zarządzać urlopem dla swojego zespołu. Zamiast tego menedżer nieobecności może obsługiwać ten proces dla członków zespołu w wielu działach i zespołach. Menedżerowie nieobecności mają następujące możliwości zarządzania urlopami:

- Przejrzyj i zatwierdź czas wolny na podstawie alternatywnej hierarchii.
- Wyświetl salda członków zespołu.
- Umożliwia wyświetlanie kalendarza nieobecności.

## <a name="turn-on-the-feature"></a>Włączanie funkcji

1. W obszarze roboczym **Administrator systemu** wybierz **Zarządzanie funkcjami**.

2. Na karcie **Zarządzanie funkcjami** włącz funkcję **(Podgląd) nieobecności, aby zarządzać funkcją urlopów**.

## <a name="define-a-custom-hierarchy"></a>Zdefiniuj niestandardową hierarchię

Funkcja menedżera nieobecności korzysta z niestandardowej hierarchii, którą należy skonfigurować.

1. W obszarze roboczym **Administrowanie organizacją** wybierz **Typy hierarchii stanowisk**.

2. Utwórz typ hierarchii stanowisk o nazwie **Urlop**.

3. W obszarze roboczym **Urlop i nieobecność** w obszarze **Łącza** wybierz **Parametry urlopu i nieobecności**.

4. Na karcie **Ogólne** z listy rozwijanej **Hierarchia nieobecności** wybierz utworzony wcześniej typ hierarchii **Urlop** . To powiązanie hierarchii urlopów musi zostać zakończone dla każdej firmy, w której będzie używana funkcja menedżera nieobecności.

Po zdefiniowaniu typu hierarchii do stanowiska musi zostać przypisany raport hierarchii stanowisk.

1. W obszarze roboczym **Administrowanie organizacją** wybierz **Wszystkie stanowiska**.

2. Wybierz stanowisko, do których ma być dodawania hierarchia urlopów.

3. Na karcie **Relacje** wybierz pozycję **Dodaj**.

4. W polu **Nazwa hierarchiię** zaznacz opcję **Urlop**.

5. W polu **Przełożony stanowiska** wybierz stanowisko. Nazwa pracownika jest wypełniana automatycznie po wybraniu stanowiska.

## <a name="assign-the-absence-manager-role-to-a-user"></a>Przypisz użytkownikowi rolę menedżera nieobecności

Rola menedżera nieobecności musi być przypisana pracownikom, aby umożliwić im zatwierdzanie lub odrzucanie wniosków urlopowych.

1. W obszarze roboczym **Administrator systemu** wybierz pozycję **Łącza**.

2. W sekcji **Użytkownicy** zaznacz łącze **Użytkownicy**.

3. Z listy użytkowników wybierz użytkownika, któremu chcesz przypisać rolę Menedżer nieobecności.

4. Na karcie **Role użytkownika** wybierz opcję **Przypisz role**.

5. Z listy wybierz rolę **Menedżer nieobecności**. Następnie wybierz opcję **OK**.

    > [!IMPORTANT]
    > Upewnij się, że rola Pracownik została również przypisana do użytkownika, któremu przypisujesz rolę Menedżer nieobecności. W przeciwnym razie pracownik nie będzie mógł korzystać z tej funkcji.

6. Po utworzeniu hierarchii opuszczania możesz ją wyświetlić, wykonując następujące kroki:

    1. W obszarze roboczym **Administrowanie organizacją** wybierz **Hierarchia stanowisk**.
    
    2. W polu **Typ hierarchii** zaznacz opcję **Urlop**.

## <a name="absence-manager-workspace"></a>Obszar roboczy menedżera nieobecności

W obszarze roboczym **Samoobsługa pracownicza** karta **Menedżer nieobecności** zawiera informacje o nieobecnościach pracowników przypisanych do menedżera nieobecności w hierarchii urlopów.

Na karcie **Urlop i nieobecność** dla każdego pracownika są dostępne następujące opcje:

- **Urlop** — Zobacz salda, zatwierdzone urlopy i wnioski urlopowe dla wybranego pracownika.
- **Salda urlopów** — zobacz listę sald dla różnych planów urlopowych dla wybranego pracownika.

## <a name="approve-time-off-requests"></a>Zatwierdź wnioski o urlop

Menedżerowie nieobecności mogą zatwierdzać lub odrzucać wnioski o urlop dla pracowników. W razie potrzeby mogą również tworzyć wnioski w imieniu pracowników.

> [!IMPORTANT]
> Zanim menedżerowie nieobecności będą mogli zatwierdzać lub odrzucać wnioski o urlop, przepływ pracy wniosków urlopowych musi być skonfigurowany tak, aby przypisywać im elementy robocze wniosków urlopowych do przeglądu.
>
> 1. Na stronie **Przepływy pracy dla zasobów ludzkich** wybierz lub utwórz przepływ pracy wniosku urlopowego.
> 2. Zaznacz opcję **Skojarz hierarchię**, a następnie w polu **Nazwa hierarchii** wybierz opcję **Urlop**.
> 3. Aktualizuj przepływ pracy w konstruktorze przepływu pracy. W obszarze **1Typ przypisania** wybierz opcję **Hierarchia**, a następnie na karcie **Wybór hierarchii** wybierz **Konfigurowalna hierarchia**.
>
> Aby uzyskać informacje na temat tworzenia przepływu pracy z wnioskiem urlopowym, zobacz temat [Tworzenie przepływu pracy wniosku o urlop](hr-leave-and-absence-workflow.md).

1. W obszarze roboczym **Samoobsługa pracowników** wybierz kartę **Menedżer nieobecności**.

2. Na karcie **Menedżer nieobecności** wybierz żądanego pracownika.

3. Wybierz **opcję Szczegóły**, a następnie wybierz opcję **Urlop**.

4. Znajdź żądanie zmiany czasu i wybierz opcję **Zatwierdzenie**. Następnie możesz wybrać opcję zatwierdzenia lub anulowania wniosku o czas wolny.

Stan **Anuluj** wskazuje, że żądanie zostało odrzucone. Stan **Ukończono** wskazuje, że żądanie zostało zatwierdzone.

## <a name="view-time-off-in-the-calendar"></a>Wyświetlanie czasu wolnego w kalendarzu

Użytkownicy pełniący rolę menedżera nieobecności mogą przeglądać prośby o urlop w swoim kalendarzu. Wykonaj poniższe czynności, aby uzyskać dostęp do kalendarza urlopów.

> [!IMPORTANT]
> Administrator systemu musi skonfigurować opcje widoku kalendarza menedżera nieobecności. Na stronie **Parametry urlopu i nieobecności**, na karcie **Kalendarz** są dostępne opcje ukrywania lub pokazywania urodzin, nieobecności bez szczegółów, urlopów i oczekujących wniosków urlopowych. Istnieje również możliwość filtrowania opcji widoku kalendarza według typu pracownika.

1. W obszarze roboczym **Samoobsługa pracownika** wybierz opcję **Menedżer nieobecności**, a następnie **Kalendarz menedżera nieobecności**.

2. W polu **Data** wpisz żądane daty.

3. W razie potrzeby zaktualizuj opcje widoku.

Kalendarz menedżera nieobecności zawiera wszystkie rekordy pracowników, którzy podlegają menedżerowi nieobecności w hierarchii urlopów.

## <a name="see-also"></a>Informacje dodatkowe

- [Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)
- [Tworzenie przepływu pracy wniosku o urlop](hr-leave-and-absence-workflow.md)
- [Wyświetlanie kalendarzy zespołów i firm](hr-employee-self-service-calendar.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
