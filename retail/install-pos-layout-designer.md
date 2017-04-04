---
title: "Instalowanie projektanta układu programu Retail POS"
description: "Za pomocą projektanta obsługiwanego jednym kliknięciem można projektować różne układy do programów Retail Modern POS (MPOS) and Cloud POS w orientacji poziomej i trybie pionowej dla różnych sklepów, kas, kasjerów i menedżerów."
author: MargoC
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: RetailTillLayout
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 219684
ms.assetid: 2e2c4eea-c6e2-4912-9832-a6b22416e39f
ms.search.region: Global
ms.search.industry: Retail
ms.author: athinesh
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: b33cbf67c00b6baea4393e82d19300085781af29
ms.lasthandoff: 03/31/2017


---

# <a name="install-the-retail-pos-layout-designer"></a>Instalowanie projektanta układu programu Retail POS

Za pomocą projektanta obsługiwanego jednym kliknięciem można projektować różne układy do programów Retail Modern POS (MPOS) and Cloud POS w orientacji poziomej i trybie pionowej dla różnych sklepów, kas, kasjerów i menedżerów.

O wyglądzie interfejsu graficznego projektowania programu MPOS lub Cloud POS decydują ustawienia układu kasowego. Układ określa położenie różnych obiektów. Przykładami są układ podsumowania, układ siatki towarów, układ odbiorcy, układ płatności oraz układ różnych przycisków menu. Układy także określają ogólny wygląd interfejsu sprzedaży wyświetlanego pracownikom.

## <a name="install-the-oneclick-designer"></a>Zainstalować oneclick designer
1.  W Microsoft Dynamics 365 dla operacji, użyj menu w lewym górnym rogu przejdź do **Retail****i handel**&gt;**konfigurację kanału**&gt;**konfiguracji punktu sprzedaży**&gt;**POS**&gt;**ekranu układy**.
2.  Zaznacz dowolny układu, który ma typ aplikacji **Modern POS for Windows** lub **Cloud POS**, a następnie kliknij przycisk **Projektant układu**.
3.  Na pasku powiadomień, który pojawia się u dołu okna programu Internet Explorer, kliknij przycisk **Otwórz** i zainstaluj projektanta obsługiwanego jednym kliknięciem. (Pasek powiadomień może pojawiać się w innych miejscach w innych przeglądarkach).
4.  W wyświetlonym oknie komunikatu **Uruchomienie aplikacji - ostrzeżenie zabezpieczeń** kliknij przycisk **Uruchom** i zainstaluj hosta projektanta programu Retail. Wskaźnik postępu pokazuje postęp procesu instalacji.
5.  Po zakończeniu instalacji przejdź do strony **Zaloguj**, wprowadź nazwę i hasło użytkownika programu Microsoft Dynamics 365 for Operations, a następnie kliknij przycisk **Zaloguj**, aby uruchomić projektanta.
6.  Po zweryfikowaniu Twoich poświadczeń i uruchomieniu projektanta możesz zaprojektować własny układ albo zmodyfikować istniejący. [![Układ w Projektancie jednym kliknięciem](./media/screenlayoutdesign_mposdownload-1024x664.png)](./media/screenlayoutdesign_mposdownload.png)

## <a name="troubleshoot-the-installation-of-the-layout-designer"></a>Rozwiązywanie problemów z instalacją projektanta układu
-   Po kliknięciu przycisku **Projektant** nie jest wyświetlany monit o pobranie (lub uruchomienie) instalatora albo Twoje obecne ustawienia zabezpieczeń nie pozwalają na pobranie pliku. **Rozwiązania:**
    -   W programie Internet Explorer upewnij się, że blokada wyskakujących okienek jest wyłączona dla tej witryny. Kliknij **ustawienia**&gt;**opcje**&gt;**prywatności**&gt;**znaleźć blokowanie wyskakujących okienek**i zmień ustawienie, jeśli konieczne jest wprowadzenie zmiany.
    -   W programie Internet Explorer dodaj adres URL programu Dynamics 365 for Operations do zaufanych witryn. Kliknij **ustawienia**&gt;**opcje**&gt;**zabezpieczeń**&gt;**Zaufane witryny**&gt;**witryny**&gt;**Dodaj**.
-   Program się nie uruchamia i wyświetlana jest instrukcja o skontaktowanie się z dostawcą. **Rozwiązanie:** W programie Internet Explorer dodaj adres URL programu Dynamics 365 for Operations do zaufanych witryn. Kliknij **ustawienie**&gt;**opcje**&gt;**zabezpieczeń**&gt;**Zaufane witryny**&gt;**witryny**&gt;**Dodaj**.

**Znany problem:** Projektant nie działa poprawnie w przeglądarkach Google Chrome i Mozilla Firefox. Pracujemy nad rozwiązaniem tego problemu.

<a name="see-also"></a>Informacje dodatkowe
--------

[Konfigurowanie, pobieranie, instalowanie i aktywowanie aplikacji Retail Modern POS](retail-modern-pos-device-activation.md)


