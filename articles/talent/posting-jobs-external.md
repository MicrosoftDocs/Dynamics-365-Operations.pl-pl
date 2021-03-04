---
title: Publikowanie ofert pracy w serwisie Broadbean z poziomu aplikacji Attract
description: W tym temacie wyjaśniono, jak korzystać z Dynamics 365 Talent - Attract do publikowania ofert pracy w Broadbean
author: pganapmsft
manager: AnnBe
ms.date: 05/16/2019
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
ms.openlocfilehash: 41fa057606887069a9ea0f1f2178eeaff59f33ca
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462277"
---
# <a name="post-jobs-to-broadbean-from-attract"></a>Publikowanie ofert pracy w serwisie Broadbean z poziomu aplikacji Attract

[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Talent: Attract pomaga uzyskać talent, którego potrzebujesz, umożliwiając publikację ofert pracy bezpośrednio z Attract do Broadbean. Po [utworzeniu pracy](./creating-jobs-attract.md) wystarczy jedno kliknięcie, aby udostępnić ofertę o pracę wszystkim potencjalnym kandydatom w Broadbean.

Publikacja ofert w Broadbean wymaga odpowiedniej licencji Broadbean. Broadbean zawiera różne produkty i plany. Aby uzyskać więcej informacji na temat licencjonowania Broadbean i cen [skontaktuj się z Broadbean](https://www.broadbean.com/contact-us/).

Jeśli jesteś administratorem, który potrzebuje więcej informacji na temat konfigurowania integracji Broadbean z Attract, przejdź do [Włącz integrację z aplikacją Broadbean w Microsoft Dynamics 365 Talent - Attract](./attract-admin-job-board-settings.md).

## <a name="post-jobs-to-broadbean"></a>Publikowanie ofert pracy w serwisie Broadbean

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
2. W karcie **Ogłoszenia** wybierz przycisk wielokropka (**...**) odpowiadający Broadbean, a następnie wybierz opcję **Wyświetl**.

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

### <a name="troubleshoot-job-posting-to-broadbean"></a>Rozwiązywanie problemów z umieszczaniem ofert w Broadbean

Jeśli masz problemy z opublikowaniem oferty pracy na Broadbean, wypróbuj poniższe rozwiązania.

1. Sprawdź, czy poświadczenia Broadbean, które zostały wprowadzone w Attract, są ważne i prawidłowe.
2. Jeśli poświadczenia są ważne i prawidłowe, skontaktuj się z [Obsługą Broadbean](https://www.broadbean.com/resources/support/).
3. Jeśli ten problem będzie nadal występował, skontaktuj się z [pomocą techniczną firmy Microsoft](./talent-support.md).

## <a name="see-also"></a>Informacje dodatkowe

[Tworzenie, zatwierdzanie i publikowanie funkcji w aplikacji Attract](./creating-jobs-attract.md)

[Włącz integrację z aplikacją Broadbean w Microsoft Dynamics 365 Talent - Attract](./attract-admin-job-board-settings.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]