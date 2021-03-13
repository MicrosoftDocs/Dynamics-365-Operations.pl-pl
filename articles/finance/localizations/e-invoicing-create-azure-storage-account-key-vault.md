---
title: Utwórz konto magazynu Azure i Magazyn kluczy
description: W tym temacie opisano sposób tworzenia konta magazynu Azure i magazynu kluczy.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: d076aa5230437d1ef90f6b46d49ee4dea526db24
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104236"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a>Utwórz konto magazynu Azure i Magazyn kluczy

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a>Wymagania wstępne

Zanim będzie można wykonać czynności opisane w tym temacie, należy upewnić się, że wykonano następujące zadania:

- Tworzenie zasobu magazynu kluczy w Azure. Aby uzyskać więcej informacji o tej funkcji, zobacz: [Informacje o usłudze Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/overview).
- Utwórz konto magazynu Azure (magazyn obiektów BLOB). Aby uzyskać więcej informacji, przejrzyj temat [Obsługa konta magazynu Azure](https://docs.microsoft.com/azure/storage/blobs/).

## <a name="overview"></a>Omówienie

W tym temacie przedstawiono dwa główne kroki:

- Skonfiguruj konto magazynu Azure, aby uzyskać identyfikator URI konta magazynu.
- Skonfiguruj Magazyn kluczy do przechowywania identyfikatora URI konta magazynu.

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a>Skonfiguruj konto magazynu Azure, aby uzyskać identyfikator URI konta magazynu

1. Umożliwia otwarcie konta magazynu, które ma być używane z dodatkiem Faktury elektroniczne.
2. Przejdź do **Usługa Blob** \> **Kontenery** i utwórz nowy kontener.
3. Wprowadź nazwę kontenera i ustaw dla pola **Poziom dostępu publicznego** wartość **Prywatne (brak dostępu anonimowego)**.
4. Otwórz kontener i przejdź do **Ustawienia \> Polityka dostępu**.
5. Wybierz opcję **Dodaj zasady**, aby dodać zapisane zasady dostępu.
6. Odpowiednio określ **Identyfikator** i pola **Uprawnień**. W polu **uprawnienia** zaznacz opcję wszystkie uprawnienia.

    ![Przyznawanie uprawnień do magazynu obiektów Blob](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. Wprowadź daty rozpoczęcia i ważności. Data ważności powinna być w przyszłości.
8. Wybierz przycisk **OK**, aby zapisać zasady, a następnie zapisz zmiany w kontenerze.
9. Wróć do konta magazynu i otwórz **Eksplorator magazynu (wersja zapoznawcza)**.
10. Kliknij prawym przyciskiem myszy kontener, a następnie wybierz polecenie **Pobierz podpis dostępu współdzielonego**.
11. W oknie dialogowym **Podpis dostępu współdzielonego** skopiuj i zapisz wartość w polu **Identyfikator URI**. Ta wartość będzie używana w następnej procedurze i jest określana jako *Identyfikator URI podpisu dostępu współdzielonego*.

    ![Wybieranie i kopiowanie wartości identyfikatora URI](media/e-Invoicing-services-create-azure-resources-select-and-copy-uri.png)

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a>Skonfiguruj Magazyn kluczy do przechowywania identyfikatora URI konta magazynu

1. Otwórz magazyn kluczy, którego zamierzasz używać z dodatkiem Faktury elektroniczne.
2. Przejdź do **Ustawienia** \> **Wpis tajny**, a następnie wybierz opcję **Generuj/Importuj**, aby utworzyć nowy wpis tajny.
3. Na stronie **Tworzenie wpisu tajnego** w polu **Opcje przekazywania** wybierz opcję **Ręcznie**.
4. Pozwala wprowadzić nazwę wpisu tajnego. Ta nazwa będzie używana podczas instalacji usługi w usłudze Regulatory Configuration Service (RCS) i będzie nazywana *nazwą klucza tajnego magazynu kluczy*.
5. W polu **Wartość** wybierz opcję **Identyfikator URI podpisu dostępu udostępnionego**, a następnie wybierz opcję **Utwórz**.
6. Skonfiguruj zasady dostępu, aby nadać dodatkowi Faktury elektroniczne odpowiedni poziom bezpiecznego dostępu do utworzonego klucza tajnego. Przejdź do **Ustawienia \> Zasad dostępu** i wybierz pozycję **Dodaj zasady dostępu**.
7. Umożliwia ustawienie tajnych uprawnień dla operacji **Rozpocznij** i **Lista**.

    ![Udzielanie dostępu do usługi](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. Umożliwia ustawienie certyfikatu uprawnień dla operacji **Rozpocznij** i **Lista**.

    ![Nadanie certyfikatu uprawnień](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. W oknie dialogowym **Główne** wybierz podmiot zabezpieczeń, dodając **Dodatek Faktury elektroniczne**.
10. Wybierz opcję **Dodaj**, a następnie wybierz opcję **Zapisz zmiany magazynu kluczy**.
11. Na stronie **Przegląd** skopiuj wartość **Nazwa DNS** dla magazynu kluczy. Ta wartość będzie używana podczas instalacji usługi w RCS i będzie określana jako *Identyfikator URI magazynu kluczy*.
