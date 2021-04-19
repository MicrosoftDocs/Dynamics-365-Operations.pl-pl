---
title: Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii
description: W tym temacie opisano sposób dodawania kodu skryptów po stronie klienta do stron witryny w celu obsługi zbierania danych telemetrycznych po stronie klienta.
author: bicyclingfool
ms.date: 09/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fb1773ab10b23a586eb6a8286f145181818585b9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797438"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a>Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób dodawania kodu skryptów po stronie klienta do stron witryny w celu obsługi zbierania danych telemetrycznych po stronie klienta.

Narzędzie Web Analytics jest podstawowym narzędziem, które umożliwia zrozumienie, w jaki sposób klienci współpracują z daną witryną, a następnie podejmujmowanie decyzji, które pozwolą zoptymalizować możliwości konwersji. Dostępnych jest wiele pakietów analiz sieci Web ułatwiających osiągnięcie tych celów, takich jak Google Analytics, Clicky, Moz Analytics, and KISSMetrics. Większość pakietów analiz sieci Web wymaga dodania kodu skryptu po stronie klienta w elemencie **\<head\>** kodu HTML na wszystkich stronach witryny.

> [!NOTE]
> Instrukcje przedstawione w tym temacie dotyczą również innych niestandardowych funkcji po stronie klienta, które Microsoft Dynamics 365 Commerce nie oferuje w sposób macierzysty.

## <a name="create-a-reusable-fragment-for-your-script-code"></a>Tworzenie fragmentu wielokrotnego użytku dla kodu skryptu

Fragment umożliwia ponowne użycie wewnętrznego lub zewnętrznego kodu skryptu na wszystkich stronach w witrynie, niezależnie od szablonu, którego używają.

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a>Tworzenie fragmentu wielokrotnego użytku dla wbudowanego kodu skryptu

Aby utworzyć fragment do ponownego użycia dla kodu skryptu wbudowanego w konstruktorze witryn, wykonaj następujące kroki.

1. Przejdź do obszaru **Fragmenty**, a następnie wybierz pozycję **Nowy**.
1. W oknie dialogowym **Nowy fragment** wybierz opcję **Skrypt wbudowany**.
1. W obszarze **Nazwa fragmentu** wprowadź nazwę fragmentu, a następnie kliknij przycisk **OK**.
1. Pod utworzonym fragmentem wybierz **Domyślny moduł skryptu wbudowanego**.
1. W okienku właściwości po prawej stronie, w obszarze **Skrypt wbudowany**, wprowadź skrypt po stronie klienta. Następnie skonfiguruj inne opcje stosownie do potrzeb.
1. Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.
1. Wybierz opcję **Publikuj**.

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a>Tworzenie fragmentu wielokrotnego użytku dla zewnętrznego kodu skryptu

Aby utworzyć fragment do ponownego użycia dla kodu skryptu zewnętrznego w konstruktorze witryn, wykonaj następujące kroki.

1. Przejdź do obszaru **Fragmenty**, a następnie wybierz pozycję **Nowy**.
1. W oknie dialogowym **Nowy fragment** wybierz opcję **Skrypt zewnętrzny**.
1. W obszarze **Nazwa fragmentu** wprowadź nazwę fragmentu, a następnie kliknij przycisk **OK**.
1. Pod utworzonym fragmentem wybierz **Domyślny moduł skryptu zewnętrznego**.
1. W okienku właściwości po prawej stronie w obszarze **Źródło skryptu** dodaj zewnętrzny lub względny adres URL dla zewnętrznego źródła skryptów. Następnie skonfiguruj inne opcje stosownie do potrzeb.
1. Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.
1. Wybierz opcję **Publikuj**.

> [!NOTE]
> Jeśli dla danej witryny jest włączona zasada zabezpieczeń zawartości (CSP), upewnij się, że wszystkie zewnętrzne adresy URL są dodane do dyrektywy **script-src** zasad CSP w module konstruktora witryn Commerce. Aby uzyskać więcej informacji, zajrzyj do [Zarządzanie zasadami zabezpieczeń zawartości (CSP)](manage-csp.md).

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a>Dodawanie fragmentu zawierającego kod skryptu do szablonu

Aby dodać fragment zawierający kod skryptu do szablonu w kreatorze witryn, wykonaj następujące kroki.

1. Przejdź do **Szablony** i otwórz szablon stron, do których chcesz dodać kod skryptu.
1. W lewym okienku rozwiń hierarchię szablonów, aby wyświetlić gniazdo **nagłówka HTML**.
1. W gnieździe **nagłówka HTML** wybierz przycisk wielokropka (**...**), a następnie wybierz **Dodaj fragment**.
1. Umożliwia wybór fragmentu utworzonego dla kodu skryptu.
1. Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.
1. Wybierz opcję **Publikuj**.

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a>Dodawanie skryptu zewnętrznego lub skryptu wbudowanego bezpośrednio do szablonu

Jeśli chcesz wstawić wewnętrzny lub zewnętrzny skrypt bezpośrednio do zbioru stron, które są kontrolowane przez jeden szablon, nie musisz najpierw utworzyć fragmentu.

### <a name="add-an-inline-script-directly-to-a-template"></a>Dodawanie skryptu wbudowanego bezpośrednio do szablonu

Aby dodać wbudowany skrypt bezpośrednio do szablonu w konstruktorze stron, należy wykonać następujące kroki.

1. Przejdź do **Szablony** i otwórz szablon stron, do których chcesz dodać kod skryptu.
1. W lewym okienku rozwiń hierarchię szablonów, aby wyświetlić gniazdo **nagłówka HTML**.
1. W gnieździe **nagłówka HTML** wybierz przycisk wielokropka (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz opcję **Skrypt wbudowany**.
1. W okienku właściwości po prawej stronie, w obszarze **Skrypt wbudowany**, wprowadź skrypt po stronie klienta. Następnie skonfiguruj inne opcje stosownie do potrzeb.
1. Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.
1. Wybierz opcję **Publikuj**.

### <a name="add-an-external-script-directly-to-a-template"></a>Dodawanie skryptu zewnętrznego bezpośrednio do szablonu

Aby dodać zewnętrzny skrypt bezpośrednio do szablonu w konstruktorze stron, należy wykonać następujące kroki.

1. Przejdź do **Szablony** i otwórz szablon stron, do których chcesz dodać kod skryptu.
1. W lewym okienku rozwiń hierarchię szablonów, aby wyświetlić gniazdo **nagłówka HTML**.
1. W gnieździe **nagłówka HTML** wybierz przycisk wielokropka (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz opcję **Skrypt zewnętrzny**.
1. W okienku właściwości po prawej stronie w obszarze **Źródło skryptu** dodaj zewnętrzny lub względny adres URL dla zewnętrznego źródła skryptów. Następnie skonfiguruj inne opcje stosownie do potrzeb.
1. Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.
1. Wybierz opcję **Publikuj**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Dodawanie logo](add-logo.md)

[Wybór motywu witryny](select-site-theme.md)

[Praca z plikami zastępowania CSS](css-override-files.md)

[Dodawanie ikony favicon](add-favicon.md)

[Dodawanie wiadomości powitalnej](add-welcome-message.md)

[Dodawanie powiadomienia o prawach autorskich](add-copyright-notice.md)

[Dodawanie języków do witryny](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
