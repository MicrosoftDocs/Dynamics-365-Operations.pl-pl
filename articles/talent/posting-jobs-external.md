---
title: Publikowanie ofert pracy z Attract na zewnętrznych stronach
description: W tym temacie wyjaśniono, jak korzystać z Dynamics 365 for Talent - Attract do publikowania ofert pracy w zewnętrznych serwisach rekrutacyjnych
author: pganapmsft
manager: AnnBe
ms.date: 03/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-03-19
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: eca599ad189edae29ef2de496196b08799a5e745
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518845"
---
# <a name="post-jobs-to-external-career-sites-from-attract"></a>Publikowanie ofert pracy z Attract na zewnętrznych stronach

[!include [banner](../includes/banner.md)]

Chcesz dotrzeć z informacją o wakacie do jak największej liczby kandydatów posiadających odpowiednie kwalifikacje. Serwisy rekrutacyjne, takie jak Broadbean mogą pomóc w osiągnięciu tych celów. Microsoft Dynamics 365 Talent: Attract umożliwia teraz publikowanie ofert pracy na Broadbean, a Microsoft stale udostępnia nowe możliwości w tym zakresie.

## <a name="post-jobs-to-broadbean"></a>Publikowanie ofert pracy na Broadbean

Przed opublikowaniem ofert pracy w Broadbean należy skonfigurować integrację Broadbean.

> [!NOTE]
> - Aby opublikować oferty pracy na zewnętrznych stronach, musisz mieć [dodatek kompleksowej obsługi rekrutacji](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).
> - Ta funkcja jest obecnie w wersjach zapoznawczych. Jeśli chcesz ją wypróbować, musisz najpierw [ją włączyć w ustawieniach administratora Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).

### <a name="configure-broadbean-integration"></a>Konfigurowanie integracji Broadbean

1. Zaloguj się w Attract jako administrator.
2. Wybierz przycisk **ustawienia** (symbol koła zębatego) w prawym górnym rogu strony, a następnie wybierz opcję **Centrum administracyjnego**.
3. Na karcie **Ustawienia tablicy funkcji** w sekcji **Włącz integrację z aplikacją Broadbean** włącz integrację.
4. Skontaktuj się z Broadbean i wprowadź informacje w **Nazwa użytkownika, identyfikator klienta, token szyfrowania**.

> [!WARNING]
> Twoje poświadczenia Broadbean są poufne. W związku z tym przechowuj je z zachowaniem odpowiednich środków ostrożności. Każda osoba z rolą administratora w Attract może wyświetlać te poświadczenia.

> [!NOTE]
> Microsoft i Attract nie uczestniczą w tworzeniu ani przechowywaniu tych wartości. Użytkownik ponosi odpowiedzialność za zachowanie aktualności danych w systemie Attract oraz współpracę z Broadbean w celu rozwiązywania wszelkich problemów związanych z jego poświadczeniami.

### <a name="post-a-job-to-broadbean"></a>Publikowanie ofert pracy na Broadbean

Po włączeniu systemu Broadbean osoby rekrutujące i administratorzy mogą publikować oferty pracy w tym systemie. Musisz mieć adres URL zgłaszania się na dane stanowisko.

1. W Attract otwórz ofertę pracy, którą chcesz opublikować na Broadbean.
2. W sekcji **Ogłoszenia** wybierz przycisk **Opublikuj teraz** odpowiadający systemowi Broadbean.
3. Wykonaj instrukcje wyświetlane w oknie Broadbean.

Attract przekazuje następujące informacje do Broadbean:

- Identyfikator zgłoszenia
- Nazwa funkcji
- Tytuł zadania
- Lokalizacja funkcji
- Adres URL do zgłaszania się
- Osoba rekrutująca

Gdy oferta zostanie opublikowana w Broadbean, sekcja **Ogłoszenia** w Attract pokaże status w Broadbean oznaczony jako **Opublikowano**.

> [!NOTE]
> - Broadbean wymaga wypełnienia pola **Branża**. Obecnie pole to jest domyślnie ustawione jako **IT**. Możesz jednak zmienić tę wartość na odpowiednią branżę w oknie publikowania oferty pracy na Broadbean.
> - Opublikowanie oferty pracy na wszystkich wybranych tablicach w Broadbean może chwilę potrwać. Z tego względu Attract może wyświetlić aktualny stan oferty pracy z pewnym opóźnieniem.

### <a name="view-a-broadbean-job-posting"></a>Wyświetlanie oferty pracy opublikowanej na Broadbean

Po opublikowaniu oferty pracy na Broadbean można ją wyświetlić w aplikacji Attract.

1. W Attract otwórz ofertę pracy, którą chcesz wyświetlić na Broadbean.
2. W sekcji **Ogłoszenia** wybierz przycisk wielokropka (**...**) odpowiadający Broadbean, a następnie wybierz opcję **Wyświetl**.

Oferta pracy opublikowana w Broadbean zostanie wyświetlona w nowym oknie.

### <a name="update-a-broadbean-job-posting"></a>Aktualizowanie oferty pracy opublikowanej na Broadbean

Ofertę pracy opublikowaną na Broadbean można zaktualizować na dwa sposoby.

1. W Attract otwórz ofertę pracy, którą chcesz zaktualizować.
2. W sekcji **Ogłoszenia** wybierz przycisk **Aktualizuj ogłoszenie** odpowiadający systemowi Broadbean.
3. Edytuj ofertę w oknie Broadbean.

– lub –

1. W Attract otwórz ofertę pracy, którą chcesz wyświetlić na Broadbean.
2. W sekcji **Ogłoszenia** wybierz przycisk wielokropka (**...**) odpowiadający Broadbean, a następnie wybierz opcję **Wyświetl**.
3. W oknie Broadbean edytuj szczegóły oferty pracy, a następnie ponownie ją opublikuj. Szczegóły oferty pracy w Attract nie ulegają zmianie.

### <a name="remove-a-broadbean-job-posting"></a>Usuwanie oferty pracy opublikowanej na Broadbean

W razie potrzeby można usunąć ofertę pracy z Broadbean.

1. W Attract otwórz ofertę pracy, którą chcesz usunąć.
2. W sekcji **Ogłoszenia** wybierz przycisk wielokropka (**...**) odpowiadający Broadbean, a następnie wybierz opcję **Usuń ogłoszenie**.

Po usunięciu ogłoszenia w Broadbean, element systemu Broadbean w Attract będzie miał przycisk **Opublikuj teraz**. Obecność tego przycisku wskazuje, że oferta została usunięta i można ją ponownie opublikować.

### <a name="troubleshoot-the-broadbean-integration"></a>Rozwiązywanie problemów z integracją Broadbean

Jeśli masz problemy z opublikowaniem oferty pracy na Broadbean, wypróbuj poniższe rozwiązania.

1. Sprawdź, czy poświadczenia Broadbean, które zostały wprowadzone w Attract, są ważne i prawidłowe.
2. Jeśli poświadczenia są ważne i prawidłowe, skontaktuj się z [Obsługą Broadbean](https://www.broadbean.com/resources/support/).
3. Jeśli ten problem będzie nadal występował, skontaktuj się z [pomocą techniczną firmy Microsoft](./talent-support.md).
