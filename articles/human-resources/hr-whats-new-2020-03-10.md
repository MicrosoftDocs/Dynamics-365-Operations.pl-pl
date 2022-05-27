---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (10 marca 2020 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 10 marca 2020 roku.
author: andreabichsel
ms.date: 03/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-03-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 831f66ef944dbe61c4dbb7833d6ec24d34aa80a3
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688441"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-10-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (10 marca 2020 r.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.2985. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.

## <a name="cant-access-skill-gap-analysis-report-394460"></a>Nie można uzyskać dostępu do raportu analizy braków kwalifikacji (394460)

Ten raport nie jest obsługiwany w rozwiązaniu Dynamics 365 Human Resources. Element menu do wydrukowania raportu SSRS został usunięty.

## <a name="incorrect-message-accessing-the-getting-started-page-417950"></a>Niepoprawna wiadomość z dostępem do strony wprowadzającej (417950)

W przypadku tej zmiany zabezpieczenia ukrywają ten element menu, jeśli nie masz dostępu do formularza.

## <a name="streamlined-task-maintenance-for-employees-380538"></a>Usprawniona konserwacja zadań dla pracowników (380538)

Formularz Obsługa zadań pracownika zawiera listę wszystkich zadań pracownika etatowego w ramach wdrażania, zwalniania, przejść i procesów biznesowych. Można teraz usunąć, zmienić przypisanie lub zaktualizować stan zadań.

Przykład: Benjamin Martin jest administratorem świadczeń. Podczas wdrażania pracownika etatowego zadania są tworzone dla Benjamina w celu przejrzenia wyboru świadczenia dla nowego pracownika. Benjamin ma przeszłe zadania, które już wykonał, i przyszłe zadania, które musi wykonać. Benjamin zdecyduje się opuścić firmę, więc jego zadania muszą zostać ponownie przypisane lub usunięte. Formularz Obsługa zadania (w okienku akcji formularza **pracownik**) umożliwia ponowne przypisanie wszystkich zadań Benjamina do innego pracownika lub ich usunięcie.  

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a>Rozwiązanie Dataverse jest teraz dostępne z następującymi zmianami:

| opis | Zmiana |
| --- | --- |
| Zmiany encji **Zatrudnienie/Stanowisko** | <ul><li>Dodano **Region wynagrodzenia**</li>|
| Dodano jednostkę **Wymiar stanowiska pracy** | <ul><li>Dodano **wymiary finansowe**</li>
| Zmiany jednostki **Pracownik** | <ul><li>Dodano **Kolejność w nazwisku**</li><li>Dodano **Pracuje z domu**</li><li>Dodano **Język**</li><li>Dodano **Data stażu pracy**</li><li>Dodano **Rocznica**</li><li>Dodano **Pierwotna data zatrudnienia**</li></ul> |
| Zmiany jednostki **Zatrudnienie** | <ul><li>Dodano **wymiary finansowe**</li><li>Dodano **Powód rozwiązania umowy**</li><li>**Data zakończenia** zmieniona z **daty przejścia**</li><li>Dodano **Okres próbny**</li></ul> |
| Zmiany jednostki **Adres Pracownika** | <ul><li>Dodano **Ulica**</li><li>**Wiersz adresu 1**, **wiersz adresu 2** i **wiersz adresu 3** oznaczone do zaniechania</li></ul> |
| Nowe jednostki ustawień wynagrodzeń o zmiennej wysokości | <ul><li>**Typ planu wynagrodzeń o zmiennej wysokości**</li><li>**Plan wynagrodzeń o zmiennej wysokości**</li><li>**Reguły wypłat**</li><li>**Poziom planu wynagrodzeń o zmiennej wysokości**</li></ul> |
| Nowa jednostka **Zatrudnienie kalendarza pracownika** | <ul><li>Dodano **jednostkę kalendarza pracy**</li></ul> |
| Nowa jednostka **Szczegół stanowiska listy płac** | <ul><li>Dodano **Szczegół stanowiska listy płac**</li></ul> |
| Nowa jednostka **Tytuł** | <ul><li>Dodano **Tytuł**</li></ul> Nowa jednostka **tytułu** jest dołączona do Dataverse, ale nie odwołuje się do w tej chwili do jednostek **stanowiska pracy** ani **Pozycji**. |

> [!NOTE]
> Wymiary finansowe dla obu stanowisk i zatrudnienia zapewniają jednokierunkową integrację aktualizacji z modułu Human Resources do usługi Dataverse. Aktualizacje wymiarów finansowych nie są obecnie synchronizowane z usługi Dataverse do modułu Human Resources.

W czasie następnych kilku tygodni zmiany tych jednostek będą dostępne we wszystkich środowiskach. Aby ręcznie zainstalować najnowsze rozwiązanie Dataverse dla modułu Human Resources:

1.  Przejdź do [Centrum administracyjnego usługi Power Platform](https://admin.powerplatform.microsoft.com).

2.  Wybierz opcję **Środowiska**.

3.  Znajdź środowisko, które chcesz uaktualnić. Środowisko powinno odpowiadać **nazwie środowiska** w sekcji **informacji programu Dataverse** w formularzu **O** w usłudze Human Resources.

4.  Wybierz środowisko, aby wyświetlić szczegóły środowiska.

5.  Wybierz przycisk **Zarządzaj rozwiązaniami** na pasku akcji u góry. Zostanie otwarte nowe okno przeglądarki i przejście do **centrum administracyjnego systemu Dynamics 365** w kontekście środowiska użytkownika.

6.  Z listy **Rozwiązanie** wybierz pozycję **Zakotwiczenie Dynamics 365 Human Resources**.

7.  Wybierz opcję **Uaktualnij**, aby zastosować najnowsze rozwiązanie.

## <a name="in-preview"></a>Wersja próbna

Następujące funkcje w wersji zapoznawczej są dostępne od 3 lutego 2020 r.:

- **Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności** — aby uzyskać więcej informacji, zobacz [Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Funkcja w wersji zapoznawczej Zarządzanie świadczeniami** — aby uzyskać więcej informacji, w tym o znanych problemach, zobacz [Omówienie obszaru roboczego Zarządzanie świadczeniami](hr-benefits-management-overview.md).

## <a name="coming-soon"></a>Wkrótce

### <a name="platform-update-33"></a>Aktualizacja platformy Update 33

- Aplikacje dla całej strony (wersja zapoznawcza) — Ta funkcja podglądu, wymagająca włączenia funkcji zapisanych widoków, zezwala na dodawanie aplikacji Power Apps, a także aplikacji innych firm jako funkcji pełnej strony za pośrednictwem pulpitu nawigacyjnego.

- Zapisane widoki (wersja zapoznawcza) — Ta funkcja podglądu włącza zapisane widoki, które są znaczącym ulepszeniem podsystemu personalizacji. Ta funkcja umożliwia użytkownikom tworzenie wielu nazwanych zestawów personalizacji na stronę. Widoki można również publikować w rolach zabezpieczeń.

- Optymalizacja „jest jedną z” funkcji filtrowania — ta funkcja umożliwia zoptymalizowane działanie „jednej z” funkcji filtrowania, co ułatwia wprowadzanie wielu wartości filtrów, ma prostszy mechanizm usuwania pojedynczych lub wszystkich wartości filtrów, a ponadto ma bardziej zwartą i intuicyjną wizualizację wartości filtrów.

- Polecane pola — użytkownicy często muszą dodawać pola do siatki lub strony. Może to być trudne przy użyciu tak wielu dostępnych pól. Zamiast wyszukiwania na dużej liście, funkcja ta pozwala systemowi na wyłonienie listy zalecanych pól na podstawie tego, co użytkownicy dodają najczęściej, w podobnych scenariuszach.

- Domyślne akcje trwałe w siatkach — ta funkcja zapewnia, że domyślna akcja w siatce jest połączona z określoną kolumną w siatce, niezależnie od tego, czy kolumna ta jest przenoszona czy ukryta.

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]