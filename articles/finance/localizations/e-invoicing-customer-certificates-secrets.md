---
title: Certyfikaty i klucze tajne klienta
description: W tym temacie wyjaśniono, jak skonfigurować certyfikaty klienta i tajemnice w fakturowaniu elektronicznym.
author: dkalyuzh
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1325cad95e9a6dc470691f5f168439fccaaa78e1
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371816"
---
# <a name="customer-certificates-and-secrets"></a>Certyfikaty i klucze tajne klienta

[!include [banner](../includes/banner.md)]

Jeśli w usłudze konfiguracji Microsoft Azure wymogów prawnych Regulatory Configuration Service (RCS) już istnieje klucz Odwołanie do klucza, można tworzyć odwołania do certyfikatów kluczy i kopii. Jeśli nie masz jeszcze odwołania do klucza, zobacz [Środowiska usług](e-invoicing-service-environments.md), aby uzyskać informacje dotyczące sposobu ich tworzenia.

## <a name="create-certificates-and-secrets"></a>Twórz certyfikaty i klucze tajne

Aby utworzyć i skonfigurować certyfikaty i klucze tajne, wykonaj następujące kroki.

1. Zaloguj się do swojego konta RCS.
2. Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Środowiska** wybierz kafelek **Faktury elektroniczne**.
3. Na stronie **Ustawienie środowiska** w okienku akcji wybierz pozycję **Środowiska usługi**.
4. Na stronie **Środowiska usługi**, w okienku akcji wybierz Środowisko usługi **Parametry Key Vault**.
5. Wybierz **Parametry wpisu tajnego**, wybierz odniesienie do klucza tajnego i w sekcji **Certyfikaty** wybierz opcję **Dodaj**.
6. W polu **Nazwa** wprowadź nazwę certyfikatu lub klucza tajnego Key Vault. Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto magazynu platformy Azure w portalu Azure](e-invoicing-create-azure-storage-account-azure-portal.md).
7. W polu **Opis wprowadź** opis.
8. W polu **Typ** wybierz pozycję **Certyfikat**, jeśli odwołujesz się do certyfikatu przechowywanego w kluczu klucza. Wybierz **klucz** tajny, jeśli odwołujesz się do tajnych danych przechowywanych w kluczu.
9. Wybierz opcję **Zapisz**.

> [!NOTE]
> W niektórych scenariuszach należy używać certyfikatów publicznych z rozszerzeniem nazwy pliku cer. Jednak klucz stornowany nie obsługuje importowania i przechowywania certyfikatów tego typu jako certyfikatów kluczy wsadowych. W tych scenariuszach należy zapisać plik .cer jako kodowany przez podstawę X.509 (. Ciąg CER). Następnie w kluczu tajnym Key Vault przechowaj ciąg, który pojawia się między wierszem **ROZPOCZNIJ CERTYFIKAT** a wierszem **ZAKOŃCZ CERTYFIKAT** w pliku. W środowisku usług wciąż należy utworzyć odwołanie do rekordu Klucz- Rekord i ustawić w polu **Typ** wartość **Certyfikat**.

## <a name="create-a-chain-of-certificates"></a>Tworzenie łańcucha certyfikatów

Jeśli faktury specyficzne dla danego kraju/regionu wymagają stosowania łańcucha certyfikatów w celu zastosowania podpisów cyfrowych lub ustanawiania bezpiecznego połączenia (Secure Sockets Layer \[SSL\]) z zewnętrznymi usługami sieci web, należy utworzyć łańcuch certyfikatów, których certyfikaty mają następującą kolejność:

1. Certyfikaty główne
2. Certyfikaty pośrednie
3. Certyfikaty użytkownika końcowego

Zaufane źródło certyfikatów to urzędy certyfikacji. Pośrednie certyfikaty certyfikacji to połączenia certyfikatów użytkownika końcowego z głównymi certyfikatami urzędu certyfikacji.

Aby utworzyć i skonfigurować łańcuch certyfikatów, wykonaj następujące kroki.

1. Na stronie **Parametry magazynu kluczy** w okienku akcji wybierz **Łańcuch certyfikatów**.
2. Wybierz pozycję **Nowy**, aby utworzyć łańcuch certyfikatów.
3. W polu **Nazwa** wprowadź nazwę łańcucha certyfikatów.
4. W polu **Opis wprowadź** opis.
5. W sekcji **Certyfikaty** wybierz pozycję **Dodaj**, aby dodać certyfikat do łańcucha.
6. Przycisk **W górę** lub **W dół** umożliwia zmianę pozycji certyfikatu w łańcuchu. U góry listy należy zachować certyfikat główny urzędu certyfikacji, a u dołu — certyfikat użytkownika końcowego.
7. Wybierz opcję **Zapisz**.

Możesz utworzyć tyle odwołań Key Vault w RCS, ile chcesz. Pamiętaj, że klucz tajny tokenu sygnatury dostępu współdzielonego (SAS) magazynu jest używany do łączenia danego środowiska usługi z odwołaniem Key Vault. Możesz odwołać się do certyfikatów Key Vault i wpisów tajnych, które są przechowywane w magazynie kluczy, który zawiera również klucz tajny tokenu SAS magazynu używanego podczas konfigurowania środowiska usługi.
