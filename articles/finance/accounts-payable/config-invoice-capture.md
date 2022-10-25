---
title: Konfigurowanie rozwiązania Invoice Capture
description: W tym artykule opisano, jak skonfigurować rozwiązanie Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: e297dafc930368f14f2e68213ce4153ba792ef4d
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691183"
---
# <a name="configure-the-invoice-capture-solution"></a>Konfigurowanie rozwiązania Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Po zainstalowaniu rozwiązania Invoice Capture należy skonfigurować środowisko. Proces ten składa się z następujących kroków podstawowych.

1. **Wymagany:** zsynchronizowanie osób prawnych z aplikacji Microsoft Dynamics 365 Finance. Ten krok służy do skonfigurowania struktury organizacji na platformie Microsoft Power Platform.
2. **Wymagany:** skonfigurowanie kanałów do importowania obrazów faktur. To rozwiązanie obsługuje następujące kanały:

    - Office 365 Outlook (domyślny)
    - Outlook.com
    - OneDrive
    - SharePoint

3. **Opcjonalny:** zdefiniowanie dodatkowych grupy konfiguracji dla usługi optycznego rozpoznawania znaków (OCR).
4. **Opcjonalny:** zdefiniowanie reguł mapowania dla osoby prawnej, konta dostawcy, pozycji i typu zaopatrzenia.

Ten artykuł koncentruje się na dwóch wymaganych krokach procesu. Aby uzyskać więcej informacji o grupach konfiguracji, zobacz temat [Grupy konfiguracji rozwiązania Invoice Capture](invoice-capture-config-group.md). Aby uzyskać więcej informacji o regułach mapowania, zobacz temat [Reguły mapowania rozwiązania Invoice Capture](invoice-capture-mapping-rules.md).

## <a name="manage-legal-entities"></a>Zarządzanie osobami prawnymi

Aplikacja Finance definiuje osoby prawne jako organizacje, które są identyfikowane przez rejestrację w urzędach. Działania biznesowe są wykonywane i rejestrowane w ramach oddzielnych osób prawnych. Na platformie Microsoft Power Platform jednostki biznesowe, role zabezpieczeń i użytkownicy są ze sobą połączeni w sposób zgodny z modelem zabezpieczeń opartych na rolach.

Jednostki biznesowe są używane razem z rolami zabezpieczeń do kontrolowania dostępu do danych. Użytkownicy widzą tylko informacje wymagane do wykonywania pracy. Rozwiązanie Invoice Capture zawiera miejsce do konfiguracji, w którym można załadować podstawowe informacje z osób prawnych istniejących w aplikacji Finance oraz zarządzać osobami prawnymi utworzonymi ręcznie. Osoby prawne są używane na fakturach od dostawcy i podczas kontroli zabezpieczeń.

Podczas tworzenia i wyświetlania osoby prawnej w widoku listy automatycznie jest tworzona domyślna jednostka biznesowa o takiej samej nazwie. Zespół ma przyznaną rolę zabezpieczeń **Urzędnik ds. rozrachunków z dostawcami**. Podczas importowania osób prawnych importowane są podstawowe dane główne z aplikacji Finance. Nieistniejące pozycje zostaną zidentyfikowane przez osobę prawną i dodane do rozwiązania Invoice Capture. Domyślna grupa konfiguracji jest przypisywana do nowych osób prawnych.

### <a name="sync-legal-entities"></a>Synchronizowanie osób prawnych

Osób prawnych nie można tworzyć bezpośrednio. Osoby prawne można jednak synchronizować z aplikację Finance. Aby zsynchronizować osoby prawne, wykonaj następujące kroki.

1. Przejdź do pozycji **Ustawienia \> Konfiguracja systemu \> Zarządzaj osobami prawnymi**.
2. Wybierz pozycję **Synchronizuj osoby prawne**, a następnie wybierz przycisk **OK** w oknie dialogowym potwierdzenia.

Po zakończeniu synchronizacji jest wyświetlana liczba nowych osób prawnych. Nowe osoby prawne są wyświetlane w widoku listy. Domyślna grupa konfiguracji jest przypisywana do nowych osób prawnych.

## <a name="configure-invoice-import-channels"></a>Konfigurowanie kanałów importowania faktur

Dostawcy wysyłają faktury z różnych kanałów (poczta e-mail, obszar roboczy plików lub portal faktur) za pomocą różnych formatów (na papierze lub w postaci obrazu). Rozwiązanie Invoice Capture może obsługiwać różne kanały i formaty. Obsługiwane są następujące typy:

- Office 365 Outlook
- Outlook.com
- SharePoint
- OneDrive

Podczas tworzenia kanału dla określonego konta zautomatyzowany przepływ ze wstępnie zdefiniowanym szablonem jest tworzony w celu monitorowania przychodzących wiadomości e-mail lub plików w skrzynce odbiorczej lub w przestrzeni. Każdy plik, który ma prawidłową fakturę, może zostać rozpoznany i wysłany do obszaru faktur, aby czekać na przetworzenie przez urzędnika ds. rozrachunków z dostawcami. Załącznik powinien być w formacie PDF lub formacie obrazu. Faktury można załadować do rozwiązania Invoice Capture zgodnie z konfiguracją kanału.

### <a name="create-a-channel"></a>Tworzenie kanału

Po zaimportowaniu dodatkowego pakietu rozwiązania (Dynamics 365 Invoice Capture — narzędzia do instalacji) domyślne połączenie programu Office 365 Outlook jest gotowe do użycia. Aby utworzyć więcej połączeń dla różnych kont e-mail lub innych typów kanałów, zobacz temat [Tworzenie dodatkowych połączeń dla kanałów](invoice-capture-advanced-settings.md#create-additional-connections-for-channels).

Aby utworzyć kanał, należy wykonać poniższe kroki.

1. Przejdź do pozycji **Ustawienia \> Konfiguracja systemu \> Konfiguruj kanały**.
2. Wybierz pozycję **Nowy**.
3. Ustaw wartości w następujących polach:

    - Nazwa kanału
    - Opis
    - Typ
    - Połączenie

Do rozwiązania można importować tylko wiadomości e-mail lub pliki, które spełniają poniższe kryteria.

| Typ               | Konfiguracja  | Więcej informacji |
|--------------------|----------------|------------------|
| Office 365 Outlook | Folder         | Folder poczty e-mail musi znajdować się w katalogu głównym. Domyślnie jest używany folder skrzynki odbiorczej. Podfolder nie jest obsługiwany. |
|                    | Filtr tematu | (Opcjonalnie) Ciąg podrzędny, który powinien być uwzględniony w temacie. |
|                    | Lokalizacja źródłowa           | (Opcjonalnie) Adres e-mail nadawcy lub nadawców. Jeśli określisz wiele adresów, użyj średnika (;) jako separatora. |
| SharePoint         | Adres witryny   | Adres URL witryny. |
|                    | Folder         | Folder w adresie witryny. |

### <a name="activate-the-channel"></a>Aktywowanie kanału

Po zapisaniu przepływu w polach jest pokazywany stan kanału oraz czas jego utworzenia. Początkowo pole **Stan** jest ustawione na **Nieaktywny**. Pole **Przyczyna stanu** wskazuje, że kanał został zainicjowany i jest gotowy do aktywacji.

Aby aktywować kanał, wybierz opcję **Aktywuj**. Pola **Stan** i **Przyczyna stanu** są aktualizowane.

Jeśli kanał nie jest wymagany, można go dezaktywować. Aby dezaktywować kanał, wybierz opcję **Dezaktywuj**. Pola **Stan** i **Przyczyna stanu** są aktualizowane.

### <a name="manage-flows-in-flow-management"></a>Zarządzanie przepływami w zarządzaniu przepływami

Kanał można wyświetlić na stronie **konfigurowania kanałów** lub w zarządzaniu przepływami.

Aby wyświetlić więcej szczegółów, przejdź do pozycji **Administrowanie systemem \> Rozwiązanie domyślne \> Przepływy w chmurze** i wybierz przepływ docelowy. Wyświetlane szczegóły obejmują połączone połączenia, właścicieli i strony przebiegów.

Aby zsynchronizować stan, wybierz pozycję **Sprawdź**, aby potwierdzić, że stan kanału odpowiada stanowi przepływu

Niektóre przypadki obsługi wyjątków są wyświetlane w polu **Przyczyna stanu**:

- **Brak połączenia usługi Dataverse** — bieżący użytkownik nie utworzył co najmniej jednego odwołania do połączenia usługi **Microsoft Dataverse**.
- **Nie znaleziono** — przepływ połączony z kanałem został usunięty w zarządzaniu przepływami. Kanał należy zapisać ponownie, aby utworzyć nowy kanał.
- **Zdezaktywowano w zarządzaniu przepływami** — przepływ został zdezaktywowany w zarządzaniu przepływami, a stan kanału różni się od stanu przepływu.
- **Aktywowano w zarządzaniu przepływami** — przepływ został aktywowany w zarządzaniu przepływami, a stan kanału różni się od stanu przepływu.
- **Wystąpił nieoczekiwany błąd** — użytkownik musi potwierdzić, że witryna jest „witryną komunikacji” i że folder to „Biblioteka dokumentów”.
