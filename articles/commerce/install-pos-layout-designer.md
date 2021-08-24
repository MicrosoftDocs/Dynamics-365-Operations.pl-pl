---
title: Instalowanie projektanta układów punktu sprzedaży
description: Za pomocą projektanta obsługiwanego jednym kliknięciem można projektować różne układy do programów Modern POS (MPOS) and Cloud POS w orientacji poziomej i trybie pionowej dla różnych sklepów, kas, kasjerów i menedżerów.
author: athinesh99
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.custom: 219684
ms.assetid: 2e2c4eea-c6e2-4912-9832-a6b22416e39f
ms.search.region: Global
ms.search.industry: Retail
ms.author: athinesh
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0d7143833bb4a98ac976ea46a1b4b21dad2f2e5841b5e142de7583b4ce6bad38
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738727"
---
# <a name="install-the-pos-layout-designer"></a>Instalowanie projektanta układów punktu sprzedaży

[!include [banner](includes/banner.md)]

Za pomocą projektanta obsługiwanego jednym kliknięciem można projektować różne układy do programów Modern POS (MPOS) and Cloud POS w orientacji poziomej i trybie pionowej dla różnych sklepów, kas, kasjerów i menedżerów.

O wyglądzie interfejsu graficznego projektowania programu MPOS lub Cloud POS decydują ustawienia układu kasowego. Układ określa położenie różnych obiektów. Przykładami są układ podsumowania, układ siatki towarów, układ odbiorcy, układ płatności oraz układ różnych przycisków menu. Układy także określają ogólny wygląd interfejsu sprzedaży wyświetlanego pracownikom.

## <a name="install-the-one-click-designer"></a>Instalowanie projektanta obsługiwanego jednym kliknięciem

1. W rozwiązaniu Commerce w menu w lewym górnym rogu wybierz kolejno opcje **Retail i Commerce** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Punkt sprzedaży** &gt; **Układy ekranu**.
2. Zaznacz dowolny układu, który ma typ aplikacji **Modern POS for Windows** lub **Cloud POS**, a następnie kliknij przycisk **Projektant układu**.
3. Na pasku powiadomień, który pojawia się u dołu okna programu Internet Explorer, kliknij przycisk **Otwórz** i zainstaluj projektanta obsługiwanego jednym kliknięciem. (Pasek powiadomień może pojawiać się w innych miejscach w innych przeglądarkach).
4. W wyświetlonym oknie komunikatu **Uruchomienie aplikacji - ostrzeżenie zabezpieczeń** kliknij przycisk **Uruchom** i zainstaluj hosta projektanta programu Retail. Wskaźnik postępu pokazuje postęp procesu instalacji.
5. Po zakończeniu instalacji na stronie **logowania** wprowadź nazwę użytkownika usługi Commerce i hasło, a następnie kliknij **Zaloguj**, aby uruchomić projektanta.
6. Po zweryfikowaniu Twoich poświadczeń i uruchomieniu projektanta możesz zaprojektować własny układ albo zmodyfikować istniejący.

    [![Układ w projektancie obsługiwanym jednym kliknięciem.](./media/screenlayoutdesign_mposdownload-1024x664.png)](./media/screenlayoutdesign_mposdownload.png)

## <a name="troubleshoot-the-installation-of-the-layout-designer"></a>Rozwiązywanie problemów z instalacją projektanta układu

- Po kliknięciu przycisku **Projektant** nie jest wyświetlany monit o pobranie (lub uruchomienie) instalatora albo Twoje obecne ustawienia zabezpieczeń nie pozwalają na pobranie pliku. 

    **Rozwiązania:**

    - W programie Internet Explorer upewnij się, że blokada wyskakujących okienek jest wyłączona dla tej witryny. Kliknij kolejno opcje **Ustawienia** &gt; **Opcje** &gt; **Prywatność** &gt; **Blokuj wyskakujące okienka** i w razie potrzeby zmień ustawienie.
    - W Internet Explorer, dodaj adres URL usługi Commerce do swoich stron zaufanych. Kliknij kolejno opcje **Ustawienia** &gt; **Opcje** &gt; **Zabezpieczenia** &gt; **Zaufane witryny** &gt; **Witryny** &gt; **Dodaj**.

- Program się nie uruchamia i wyświetlana jest instrukcja o skontaktowanie się z dostawcą.

    **Rozwiązanie:** W Internet Explorer dodaj adres URL usługi Commerce do swoich stron zaufanych. Kliknij kolejno opcje **Ustawienia** &gt; **Opcje** &gt; **Zabezpieczenia** &gt; **Zaufane witryny** &gt; **Witryny** &gt; **Dodaj**.

**Znany problem:** Projektant nie działa poprawnie w przeglądarkach Google Chrome i Mozilla Firefox. Pracujemy nad rozwiązaniem tego problemu.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie, instalowanie i aktywacja Retail Modern POS (MPOS)](retail-modern-pos-device-activation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]