---
title: Błąd ścieżki certyfikacji podczas konfigurowania połączenia z aplikacją
description: Jeśli w aplikacji Warehouse Management wyświetlany jest błąd „Nie znaleziono kotwicy zaufania dla ścieżki certyfikacji”, użyj tej strony, aby znaleźć rozwiązanie lub obejście tego problemu.
author: ivanv-microsoft
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: WMA
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e4a36874ac4982c9c92a7dcc17c13c7c7c02bf8c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477311"
---
# <a name="trust-anchor-for-certification-path-not-found-when-setting-up-app-connection"></a>Nie znaleziono kotwicy zaufania dla ścieżki certyfikacji podczas konfigurowania połączenia z aplikacją

## <a name="symptoms"></a>Objawy

Podczas próby nawiązania połączenia aplikacji Supply Chain Management z aplikacją Warehouse Management wyświetlić następujący komunikat o błędzie:

> java.security.cert.certPathValidatorException: nie znaleziono kotwicy zaufania dla ścieżki certyfikacji.

Ten problem może wpłynąć na urządzenia mające następujące właściwości:

- **Wersja systemu operacyjnego:** Android 4.4.x (na przykład Zebra TC55). To nie jest problem w przypadku najnowszych wersji systemu Android.
- **Lokalizacja aplikacji Supply Chain Management**: chmura
- **Tryb połączenia**: klucz tajny klienta lub certyfikat

## <a name="possible-cause"></a>Możliwa przyczyna

Microsoft może zaktualizować certyfikaty SSL używane przez aplikację Supply Chain Management. W związku z tym certyfikat główny i/lub jeden z certyfikatów pośrednich mógł się zmienić, więc nowy certyfikat nie znajduje się na liście zaufanych certyfikatów systemowych dla urządzenia przenośnego. Nowsze wersje systemu Android automatycznie aktualizują listy zaufanych certyfikatów, ale system Android 4.4.x tego nie robi.

## <a name="resolution"></a>Rozwiązanie

Wykonaj jeden z poniższych kroków, aby rozwiązać ten problem:

- W celu zaktualizowania poszczególnych odpowiednich urządzeń skorzystaj z obejścia opisanego w następnej sekcji.
- W celu uzyskania aktualizacji certyfikatów zaufanego urzędu certyfikacji (CA) dla systemu może okazać się *możliwe* skontaktowanie z firmą Zebra lub Google. Nie jest to jednak potwierdzone.
- Jeśli to możliwe, należy rozważyć zastąpienie starszych urządzeń urządzeniami, na których jest uruchomiona nowsza wersja systemu Android (gdzie zaufane certyfikaty urzędu certyfikacji są aktualizowane automatycznie).

### <a name="workaround"></a>Obejście

#### <a name="step-1-export-the-new-root-certificate-from-supply-chain-management"></a>Krok 1. Eksportowanie nowego certyfikatu głównego z aplikacji Supply Chain Management

Ręcznie pobierz nowy certyfikat główny za pomocą przeglądarki internetowej, wykonując następujące czynności:

1. Zaloguj się do aplikacji Dynamics Supply Chain Management i otwórz stronę główną.

1. Na pasku adresu przeglądarki wybierz ikonę blokady, aby otworzyć okno dialogowe **Lokalizacja jest bezpieczna**.
1. W oknie dialogowym wybierz opcję **Certyfikat (ważny)**, aby otworzyć okno **Certyfikat** dla tego certyfikatu.
1. Otwórz kartę **Ścieżka certyfikatu** w oknie **Certyfikat**.
1. Wybierz główny certyfikat wyświetlany w hierarchii. (jest to certyfikat główny).
1. Otwórz kartę **Szczegóły** w oknie **Certyfikat**.
1. Wybierz przycisk **Kopiuj do pliku** u dołu karty **Szczegóły**.
1. Zostanie otwarty **Kreator eksportu certyfikatu**. Wybierz przycisk **Dalej**, aby kontynuować.
1. Zostanie otwarta strona **Format pliku eksportu**. Wybierz opcję **Zakodowany plik binarny DER X.509 (CER)**. Następnie wybierz przycisk **Dalej**, aby kontynuować.
1. Zostanie otwarta strona **Pliki do eksportu**, określ nazwę i lokalizację pliku. Następnie wybierz przycisk **Dalej**, aby kontynuować.
1. Zostanie otwarta strona **Kończenie pracy z kreatora eksportu certyfikatów**, na której jest pokazywany wynik eksportu. Wybierz **Zakończ**.

#### <a name="step-2-install-the-downloaded-certificate-onto-the-affected-devices"></a>Krok 2. Instalowanie pobranego certyfikatu na urządzeniach, których dotyczy problem

Zainstaluj pobrany certyfikat, wykonując następujące czynności:

1. Przenieś certyfikat pobrany w poprzednim kroku na urządzenie, które chcesz zaktualizować. Na przykład, aby udostępnić plik na urządzeniu, można użyć karty SD lub połączenia sieciowego.
1. Otwórz ustawienia zabezpieczeń dla tego urządzenia i wybierz opcję menu, aby zainstalować certyfikat z pliku. (Dokładne kroki różnią się w zależności od urządzenia i wersji systemu operacyjnego).
1. Nowy certyfikat powinien być teraz widoczny na karcie **Użytkownik** dla zaufanych certyfikatów.
1. Powtórz tę procedurę dla każdego urządzenia, którego dotyczy problem.
