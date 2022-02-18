---
title: Konfigurowanie roli menedżera nieobecności
description: W tym temacie wyjaśniono, jak skonfigurować rolę menedżera nieobecności do zarządzania urlopami pracowniczymi.
author: hasrivas
ms.date: 08/25/2021
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
ms.openlocfilehash: 9f1c699358c9cc8de9e975886cfb72edfb0d3f31
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065233"
---
# <a name="configure-the-absence-manager-role"></a>Konfigurowanie roli menedżera nieobecności


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W niektórych organizacjach menedżerowie osób mogą nie zarządzać urlopem dla swojego zespołu. Zamiast tego menedżer nieobecności może obsługiwać ten proces dla członków zespołu w wielu działach i zespołach. Menedżerowie nieobecności mają następujące możliwości zarządzania urlopami:

- Przejrzyj i zatwierdź czas wolny na podstawie alternatywnej hierarchii.
- Wyświetl salda członków zespołu.
- Umożliwia wyświetlanie kalendarza nieobecności.

## <a name="turn-on-the-feature"></a>Włączanie funkcji

1. W obszarze roboczym **Administrator systemu** wybierz **Zarządzanie funkcjami**.

2. Na karcie **Zarządzanie funkcjami** włącz funkcję **nieobecności, aby zarządzać funkcją urlopów**.

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

W obszarze roboczym **Samoobsługa pracownicza** karta **Menedżer urlopów** zawiera informacje o nieobecnościach pracowników przypisanych do menedżera nieobecności w hierarchii urlopów. Menedżer nieobecności oferuje kilka opcji: 
 - Przeglądanie wniosków o czas wolny.</br>
 - Złożyć wniosek o czas wolny w imieniu pracownika.</br>
 - Wyświetlanie wszystkich pracowników przypisanych do nich w ramach hierarchii urlopów.</br>
 - Wyświetl kalendarz menedżera nieobecności.</br>

W obszarze roboczym **Zarządzanie urlopem** znajdują się dwie karty:
 - **Prośby o czas wolny**: Ta karta wyświetli listę wszystkich oczekujących żądań wolnych od czasu, które menedżer nieobecności może zatwierdzić. Menedżer nieobecności może wybrać wiele rekordów i podjąć działania na nich w tym samym czasie. Jeśli międzyfirmowy widok urlopu jest włączony, ta lista będzie wyświetlać oczekujące żądania wolnego czasu we wszystkich firmach, do których mają dostęp. W przeciwnym razie zostanie wyświetlona oczekująca liczba żądań wolnych od pracy dla aktualnie wybranej firmy. </br>
 - **Wszyscy pracownicy**: Ta karta wyświetli listę wszystkich pracowników przypisanych do menedżera nieobecności w hierarchii urlopów. Dla każdego pracownika dostępnych jest kilka opcji:
    - **Prośba o czas wolny** — prześlij nowe żądanie wolnego czasu dla wybranego pracownika.</br>
    - **Urlop** — Zobacz salda, zatwierdzone urlopy i wnioski urlopowe dla wybranego pracownika.</br>

## <a name="approve-time-off-requests"></a>Zatwierdź wnioski o urlop

Menedżerowie nieobecności mogą zatwierdzać lub odrzucać wnioski o urlop dla pracowników. 

> [!IMPORTANT]
> Zanim menedżerowie nieobecności będą mogli zatwierdzać lub odrzucać wnioski o urlop, przepływ pracy wniosków urlopowych musi być skonfigurowany tak, aby przypisywać im elementy robocze wniosków urlopowych do przeglądu.
>
> 1. Na stronie **Przepływy pracy dla zasobów ludzkich** wybierz lub utwórz przepływ pracy wniosku urlopowego.
> 2. Zaznacz opcję **Skojarz hierarchię**, a następnie w polu **Nazwa hierarchii** wybierz opcję **Urlop**.
> 3. Aktualizuj przepływ pracy w konstruktorze przepływu pracy. W obszarze **1Typ przypisania** wybierz opcję **Hierarchia**, a następnie na karcie **Wybór hierarchii** wybierz **Konfigurowalna hierarchia**.
>
> Aby uzyskać informacje na temat tworzenia przepływu pracy z wnioskiem urlopowym, zobacz temat [Tworzenie przepływu pracy wniosku o urlop](hr-leave-and-absence-workflow.md).

1. W obszarze roboczym **Samoobsługa pracowników** wybierz kartę **Menedżer urlopów**.

2. Na karcie **Prośby o czas wolny** wybierz czas wolny od żądań, na których chcesz podjąć działania. W tym widoku listy można wybrać wiele rekordów.

3. Użyj przycisków akcji w górnej części siatki, aby zatwierdzić, odmówić lub delegować żądanie wolnego czasu. 

Alternatywnie użytkownik może również użyć kafelka **Prośby o czas wolny** po lewej stronie, aby przejść do listy wszystkich elementów pracy żądania czasu wolnego. 

## <a name="view-time-off-in-the-calendar"></a>Wyświetlanie czasu wolnego w kalendarzu

Użytkownicy pełniący rolę menedżera nieobecności mogą przeglądać prośby o urlop w swoim kalendarzu. Wykonaj poniższe czynności, aby uzyskać dostęp do kalendarza urlopów.

> [!IMPORTANT]
> Administrator systemu musi skonfigurować opcje widoku kalendarza menedżera nieobecności. Na stronie **Parametry urlopu i nieobecności**, na karcie **Kalendarz** są dostępne opcje ukrywania lub pokazywania urodzin, nieobecności bez szczegółów, urlopów i oczekujących wniosków urlopowych. Istnieje również możliwość filtrowania opcji widoku kalendarza według typu pracownika.

1. W obszarze roboczym **Samoobsługa pracownika** wybierz opcję **Menedżer urlopów**, a następnie **Kalendarz menedżera nieobecności**.

2. W polu **Data** wpisz żądane daty.

3. W razie potrzeby zaktualizuj opcje widoku.

Kalendarz menedżera nieobecności zawiera wszystkie rekordy pracowników, którzy podlegają menedżerowi nieobecności w hierarchii urlopów.

## <a name="see-also"></a>Informacje dodatkowe

- [Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)
- [Tworzenie przepływu pracy wniosku o urlop](hr-leave-and-absence-workflow.md)
- [Wyświetlanie kalendarzy zespołów i firm](hr-employee-self-service-calendar.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
