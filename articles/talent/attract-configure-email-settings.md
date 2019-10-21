---
title: Skonfiguruj ustawienia wiadomości e-mail w Microsoft Dynamics 365 Talent - Attract
description: W tym temacie wyjaśniono, jak skonfigurować ustawienia wiadomości e-mail wysyłanych przez Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: c891a36f01d36774bd921475fa5995d207cd2d51
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008669"
---
# <a name="configure-email-settings"></a>Konfigurowanie ustawień poczty e-mail

[!include[banner](../includes/banner.md)]

Twoja marka buduje zaufanie i pomaga budować relacje z kandydatami, zanim nawet zaczną starać się o stanowiska. Pozytywne postrzeganie marki przyciąga największe talenty i zwiększa lojalność obecnych pracowników. Microsoft Dynamics 365 Talent: Attract pozwala ci skonfigurować wiadomości e-mail w taki sposób, który będzie najlepiej wyraźał markę Twojej firmy. W związku z tym możesz zapewnić spójne doświadczenie kandydatom w trakcie procesu aplikacji.

Attract pozwala wykonać następujące akcje:

- Skonfiguruj ustawienia poczty e-mail, aby korzystać z konta usługi poczty e-mail Microsoft Exchange dla Twojej firmy. W ten sposób kandydaci wiedzą, że wiadomości e-mail pochodzą z Twojej firmy. Na przykład możesz skonfigurować ustawienia, aby kandydaci otrzymywali wiadomości e-mail od `recruiting@contoso.com` zamiast `contoso@microsoft.com`.
- Stwórz spójną markę dla wszystkich wiadomości e-mail, ustawiając globalny nagłówek i stopkę dla szablonów wiadomości e-mail. 

> [!NOTE]
> Skonfiguruj aplikację Attract, aby korzystała z konta usługi e-mail Twojej firmy do wysyłania wiadomości e-mail, potrzebny jest kompleksowy dodatek zatrudniania.

## <a name="connect-an-email-service-account"></a>Połącz konto wiadomości e-mail

Poprzez połaczenie konta e-mail Twojej firmy, możesz stworzyć wyjątkowo spójne doświadczenie dla kandydatów. Jeśli nie połączysz konta e-mail Twojej firmy, aplikacja Attract automatycznie używa konta z nazewnictwem Microsoft.

1. Wybierz **Ustawienia** (symbol koła zębatego w prawym górnym rogu), a następnie wybierz **Centrum administracji**.
2. W karcie **Ustawienia e-mail** pod **Konta e-mail** wybierz **Połącz konto firmowe**.

    ![Połącznienie Twojego firmowego konta e-mail w aplikacji Attract](./media/attract-admin-email-service-accounts.png)

    Więcej informacji na temat tworzenia wspólnego konta e-mail znajdziesz: [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).

3. Zaloguj się w oknie logowania Microsoft używając firmowych danych.
4. Jeśli nie skonfigurowałeś jeszcze konta usługi e-mail lub chcesz dodać nowe, wybierz **Dodaj nowe konto usługi**, a następnie wprowadź dane konta e-mail. Jeśli masz już skonfigurowane konto usługi e-mail, którego chcesz użyć, wybierz je.

Po pomyślnym skonfigurowaniu konta usługi e-mail, znajdziesz je w **Konta e-mail**.

## <a name="disconnect-an-email-service-account"></a>Odłącz konto wiadomości e-mail

Jeśli chcesz zaprzestać korzystania z domeny firmy w komunikacji e-mail w aplikacji Attract, możesz odłączyć konto usługi e-mail.

1. Wybierz **Ustawienia** (symbol koła zębatego w prawym górnym rogu), a następnie wybierz **Centrum administracji**.
2. W karcie **Ustawienia e-mail** pod **Konta e-mail** wybierz przycisk **Więcej** (trzy pionowe kropki) obok konta usługi e-mail, które chcesz rozłączyć.
3. Wybierz **Odłącz konto e-mail**

    ![Odłączanie firmowego konta e-mail](./media/attract-admin-disconnect-email-account.png)

4. Gdy pojawi się prośba o potwierdzenie operacji, wybierz **Odłącz**.

    ![Potwierdzenie odłączenia firmowego konta e-mail](./media/attract-admin-email-confirm-disconnect.png)

Jeśli nie połączysz innego konta e-mail, aplikacja Attract automatycznie używa konta z nazewnictwem Microsoft.

## <a name="configure-email-template-settings"></a>Skonfiguruj ustawienia szablonów e-mail

Możesz przesłać obraz logo swojej firmy i inne informacje w postaci nagłówka oznaczonego marką dla wiadomości e-mail. Możesz również podać linki do swojej polityki prywatności i warunków korzystania w stopkach wiadomości e-mail.

> [!NOTE]
> Musisz przestrzegać wszystkich obowiązujących przepisów prawa w Twoim kraju lub regionie, a także kraju lub regionu odbiorcy wiadomości e-mail. Przepisy te obejmują przepisy antyspamowe.

1. Wybierz **Ustawienia** (symbol koła zębatego w prawym górnym rogu), a następnie wybierz **Centrum administracji**.
2. Na karcie **Ustawienia e-mail** pod **Ustawienia szablonów wiadomości e-mail**, przeciągnij obraz, którego chcesz użyć jako nagłówka wiadomości e-mail, do pola obrazu lub kliknij pole obrazu, aby wyszukać plik. Aby zastąpić istniejący obraz, musisz najpierw wybrać opcję **Usuń** obok niego. Obraz musi być w formacie JPEG, JPG, PNG, lub SVG. Zalecany rozmiar dla obrazów wynosi od 25 do 800 pikseli szerokości i od 25 do 150 pikseli wysokości. Maksymalny rozmiar pliku nagłówka wynosi 1 megabajt (MB).

    ![Dodawanie obrazu do nagłówka wiadomości e-mail Twojej firmy](./media/attract-admin-email-header.png)

3. Pod adresem **Twoja polityka prywatności dotycząca komunikacji** podaj link do polityki prywatności firmy. Pod adresem **Twoje zasady i warunki dotyczące komunikacji** podaj link do zasad i warunków firmy.

    ![Dodawanie linków do polityki prywatności i warunków korzystania firmy w stopkach wiadomości e-mail.](./media/attract-admin-email-footer.png)

4. Wybierz **Zapisz**, żeby zapisać ustawienia szablonu e-mail.
