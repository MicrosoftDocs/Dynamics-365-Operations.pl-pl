---
title: Rozwiązywanie problemów z konfiguracją i instalacją Store Commerce
description: W tym artykule opisano sposób rozwiązywania problemów z konfiguracją i instalacją aplikacji Microsoft Dynamics 365 Commerce Store Commerce.
author: josaw1
ms.date: 06/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: e3d115e84af1aaf5266eff6588ca6996a333e51a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286338"
---
# <a name="troubleshoot-store-commerce-setup-and-installation-issues"></a>Rozwiązywanie problemów z konfiguracją i instalacją Store Commerce

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób rozwiązywania problemów z konfiguracją i instalacją aplikacji Microsoft Dynamics 365 Commerce Store Commerce.

## <a name="i-cant-activate-the-app-and-i-receive-a-connectivity-error-message"></a>Nie można aktywować aplikacji i pojawia się komunikat o błędzie łączności

Po wprowadzeniu poprawnego adresu URL Cloud Point of Sale (CPOS) może pojawić się komunikat o błędzie połączenia, przypominający poniższy przykład:

> Wystąpił błąd łączności i to urządzenie nie może nawiązać połączenia z programem CPOS. Wpisany adres URL systemu CPOS może mieć pewne problemy.

W takim przypadku należy sprawdzić, czy w adresie URL nie ma błędów typograficznych, lub ustalić, czy z systemem CPOS nie można się skontaktować, ponieważ jest on w trybie offline.

Ponadto należy sprawdzić, czy wersja Cloud Scale Unit (CSU) to 10.0.25 (9.35.\*.\*) lub nowsza. Do korzystania z aplikacji Store Commerce wymagany jest system CPOS w wersji 10.0.25 lub nowszej.

## <a name="i-cant-install-the-app-because-modern-pos-is-already-installed"></a>Nie można zainstalować aplikacji, ponieważ program Modern POS jest już zainstalowany

Podczas instalacji może zostać wyświetlony komunikat o błędzie, taki jak w poniższym przykładzie:

> Wersja (9.\*.\*.\*) tego produktu (Modern POS) została wcześniej zainstalowana za pośrednictwem starszego Instalatora.

Aby usunąć błąd, należy odinstalować aplikację Modern Point of Sale (MPOS) dla wszystkich użytkowników na komputerze, a następnie spróbować ponownie. Możesz sprawdzić, czy system MPOS został usunięty dla wszystkich użytkowników, wykonując następujące polecenie PowerShell.

```PowerShell
Get-AppxPackage | Where-Object {$_.PackageFullName -like "Microsoft.Dynamics.*.Pos"} | Remove-AppxPackage -Allusers
```

## <a name="i-cant-activate-the-app-because-of-an-invalid-url-or-an-error-state"></a>Nie mogę aktywować aplikacji z powodu nieprawidłowego adresu URL lub stanu błędu

Jeśli wprowadzony adres URL CPOS nie jest prawidłowy i chcesz go zmienić lub jeśli podczas aktywacji w aplikacji Store Commerce wystąpił błąd, możesz ponownie uruchomić proces, resetując aplikację. Aplikacja Store Commerce zapisze tylko prawidłowy adres URL CPOS.

Aby zresetować aplikację Store Commerce, wykonaj następujące kroki.

1. W menu **Start** systemu Windows wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) aplikację, a następnie wybierz polecenie **Więcej \> Ustawienia aplikacji**.
2. Przewiń w dół stronę ustawień aplikacji, dopóki nie znajdziesz przycisku **Resetuj**.
3. Wybierz **Resetuj**. Następnie, po wyświetleniu monitu, potwierdź, że chcesz zresetować aplikację.
