---
title: Konfigurowanie zasobów platformy Azure dla analizy Internetu rzeczy (IoT)
description: W tym temacie opisano sposób tworzenia i konfigurowania zasobów platformy Microsoft Azure potrzebnych do przeprowadzania analizy Internetu rzeczy (IoT).
author: robinarh
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 33c28f8e7982c6ec9b892e975525de69fc637892
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881379"
---
# <a name="set-up-azure-resources-for-iot-intelligence"></a>Konfigurowanie zasobów platformy Azure dla analizy Internetu rzeczy (IoT)

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób tworzenia i konfigurowania zasobów platformy Microsoft Azure potrzebnych do przeprowadzania analizy Internetu rzeczy (IoT).

## <a name="create-azure-resources"></a>Tworzenie zasobów platformy Azure

Aby utworzyć centrum IoT, pamięć podręczną Redis i magazyn kluczy, do których można uzyskać dostęp z poziomu aplikacji Microsoft Dynamics 365 Supply Chain Management, wykonaj poniższe kroki.

### <a name="verify-that-the-microsoft-dynamics-erp-microservices-first-party-app-id-is-in-your-tenant"></a>Sprawdź, czy identyfikator naszej aplikacji mikrousług Microsoft Dynamics ERP znajduje się w Twojej dzierżawie

Aby sprawdzić, czy identyfikator naszej aplikacji mikrousług Microsoft Dynamics ERP znajduje się w Twojej dzierżawie, wykonaj następujące kroki.

1. Zaloguj się do portalu Azure pod adresem <https://portal.azure.com>.
2. Przejdź do **Azure Active Directory**.
3. Przejdź do obszaru **Aplikacje dla przedsiębiorstw**.
4. W polu **Typ aplikacji** wybierz pozycję **Aplikacje firmy Microsoft**.
5. W polu wyszukiwania wprowadź **Mikrousługi Microsoft Dynamics ERP**.
6. Sprawdź, czy pozycja **Mikrousługi Microsoft Dynamics ERP** znajduje się na liście. Inne aplikacje mają podobne nazwy. Dlatego upewnij się, że znaleziona aplikacja jest prawidłowa. Identyfikator aplikacji to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.

    Jeśli aplikacji nie ma na liście, musisz ją dodać do dzierżawy:

    1. W witrynie Azure Portal kliknij na pasku narzędzi przycisk, aby otworzyć usługę Azure Cloud Shell.
    2. Uruchom polecenie **Install-Module AzureAD**. Wprowadź wartość **Y**, aby zainstalować moduł.
    3. Uruchom polecenie **Get-InstalledModule -Name "AzureAD"**, aby sprawdzić, czy moduł został zainstalowany.
    4. Uruchom polecenie **Connect-AzureAD -Confirm**, aby uruchomić uwierzytelnianie.
    5. Uruchom polecenie **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.

    Teraz możesz powtórzyć kroki od 1 do 6, aby sprawdzić, czy identyfikator aplikacji znajduje się w dzierżawie.

### <a name="create-a-key-vault-resource"></a>Tworzenie zasobu magazynu kluczy

Aby utworzyć zasób magazynu kluczy, wykonaj poniższe kroki.

1. W witrynie Azure Portal utwórz grupę zasobów lub przejdź do niej.
2. Wybierz opcję **Dodaj**.
3. Na stronie **Nowy** w polu wyszukiwania wprowadź ciąg **Magazyn kluczy**. Następnie wybierz opcję **Utwórz**.
4. Na stronie **Tworzenie magazynu kluczy** w polu **Nazwa magazynu kluczy** wprowadź nazwę.
5. Przejrzyj wartości domyślne, a następnie wybierz pozycję **Przegląd + tworzenie**.
6. Wybierz opcję **Utwórz**.

Magazyn kluczy jest tworzony w tle.

### <a name="create-an-iot-hub-resource"></a>Tworzenie zasobu centrum IoT

Aby utworzyć zasób centrum IoT, wykonaj poniższe kroki.

1. Wybierz grupę zasobów lub przejdź do niej.
2. Wybierz opcję **Dodaj**.
3. Na stronie **Nowy** w polu wyszukiwania wprowadź ciąg **Centrum IoT**. Następnie wybierz opcję **Utwórz**.
4. W polu **Nazwa centrum IoT** wprowadź nazwę.
5. Przejrzyj wartości domyślne, a następnie wybierz pozycję **Przegląd + tworzenie**.
6. Wybierz opcję **Utwórz**.

Centrum IoT jest tworzone w tle.

> [!NOTE]
> Zalecamy, aby dla każdego środowiska utworzyć tylko jeden zasób typu centrum IoT.

### <a name="create-a-redis-cache-resource"></a>Tworzenie zasobu pamięci podręcznej Redis

Aby utworzyć zasób pamięci podręcznej Redis, wykonaj poniższe kroki.

1. Wybierz grupę zasobów lub przejdź do niej.
2. Wybierz opcję **Dodaj**.
3. Na stronie **Nowy** w polu wyszukiwania wprowadź ciąg **Azure Cache for Redis**. Następnie wybierz opcję **Utwórz**.
4. W polu **Nazwa DNS** wprowadź nazwę.
5. Przejrzyj wartości domyślne, a następnie wybierz pozycję **Utwórz**.

Pamięć podręczna Redis jest tworzona w tle.

> [!NOTE]
> Zalecamy, aby dla każdego środowiska utworzyć tylko jedną pamięć podręczną Redis.

Wszystkie zasoby zostały teraz utworzone.

## <a name="configure-the-azure-resources"></a>Konfigurowanie zasobów platformy Azure

### <a name="configure-the-iot-hub"></a>Konfigurowanie centrum IoT

Aby skonfigurować centrum IoT, wykonaj następujące kroki.

1. W obszarze zasobów wybierz zasób Centrum IoT.
2. W lewym okienku nawigacji wybierz pozycję **Wbudowane punkty końcowe**.
3. W obszarze **Grupy konsumentów** wklej następujące grupy konsumentów: Te grupy odbiorców odpowiadają gotowym scenariuszom.

    + microsoft.dynamics.iotintelligence-1
    + microsoft.dynamics.iotintelligence-2
    + microsoft.dynamics.iotintelligence-3

### <a name="configure-the-key-vault"></a>Konfigurowanie magazynu kluczy

Aby skonfigurować magazyn kluczy, wykonaj następujące kroki.

1. W obszarze zasobów wybierz zasób Magazyn kluczy.
2. W okienku nawigacji po lewej stronie wybierz pozycję **Zasady dostępu**.
3. Wybierz pozycję **Dodaj zasady dostępu**.
4. Na stronie **Dodawanie zasad dostępu** w polu **Uprawnienia klucza tajnego** wybierz pozycję **Pobieranie** i **Tworzenie listy**.
5. Kliknij w obszarze **Wybierz podmiot zabezpieczeń**.
6. W oknie dialogowym **Podmiot zabezpieczeń** wyszukaj i wybierz pozycję **Mikrousługi Microsoft Dynamics ERP**. Następnie wybierz pozycję **Wybierz**.
7. Wybierz opcję **Dodaj**.
8. Wybierz opcję **Zapisz**.

Aplikacja ma teraz dostęp do kluczy tajnych w magazynie kluczy.

### <a name="save-the-iot-hub-connection-string-secret"></a>Zapisywanie klucza tajnego parametrów połączenia centrum IoT

Aby zapisać klucz tajny dla parametrów połączenia centrum IoT, wykonaj następujące kroki.

1. W obszarze zasobów wybierz zasób Centrum IoT.
2. W lewym okienku nawigacji wybierz pozycję **Wbudowane punkty końcowe**.
3. Skopiuj wartość w polu **Punkt końcowy zgodny z centrum zdarzeń**.
4. Przejdź do zasobu magazynu kluczy.
5. W okienku nawigacji po lewej stronie wybierz pozycję **Wpisy tajne**.
6. Wybierz pozycję **Generuj/importuj**.
7. W polu **Nazwa** wprowadź nazwę.
8. W polu **Wartość** wklej wcześniej skopiowaną wartość punktu końcowego.
9. Wybierz opcję **Utwórz**.

### <a name="save-the-redis-cache-connection-string-secret"></a>Zapisywanie klucza tajnego parametrów połączenia pamięci podręcznej Redis

Aby zapisać klucz tajny dla parametrów połączenia pamięci podręcznej Redis, wykonaj następujące kroki.

1. W obszarze zasobów wybierz zasób pamięci podręcznej Redis.
2. Wybierz pozycję **Klucze dostępu**.
3. Skopiuj wartość w polu **Podstawowe parametry połączenia**.
4. Przejdź do zasobu magazynu kluczy.
5. W okienku nawigacji po lewej stronie wybierz pozycję **Wpisy tajne**.
6. Wybierz pozycję **Generuj/importuj**.
7. W polu **Nazwa** wprowadź nazwę.
8. W polu **Wartość** wklej wcześniej skopiowane parametry połączenia.
9. Wybierz opcję **Utwórz**.

> [!NOTE]
> Za każdym razem, gdy parametry połączenia są aktualizowane, musisz również zaktualizować wartości kluczy tajnych.

Aprowizowanie wymaganych zasobów platformy Azure zostało zakończone. Następny krok to [zainstalowanie dodatku analizy Internetu rzeczy (IoT) w usługach Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
