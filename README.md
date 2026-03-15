<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>权限请求演示</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
        }
        body {
            background: #f5f5f5;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }
        .auth-card {
            background: white;
            width: 100%;
            max-width: 380px;
            padding: 30px 25px;
            border-radius: 16px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.08);
        }
        .auth-title {
            font-size: 20px;
            font-weight: 600;
            color: #333;
            margin-bottom: 20px;
            text-align: center;
        }
        .auth-content {
            font-size: 16px;
            color: #555;
            line-height: 1.6;
            margin-bottom: 25px;
        }
        .user-agreement {
            font-size: 12px;
            color: #999;
            text-align: center;
            margin-bottom: 30px;
        }
        .btn-group {
            display: flex;
            gap: 12px;
        }
        .btn {
            flex: 1;
            padding: 12px 0;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s;
        }
        .btn-allow {
            background: #007AFF;
            color: white;
        }
        .btn-allow:active {
            background: #0056CC;
        }
        .btn-refuse {
            background: #f2f2f2;
            color: #666;
        }
        .tip {
            margin-top: 20px;
            padding: 12px;
            border-radius: 8px;
            font-size: 14px;
            text-align: center;
            display: none;
        }
        .tip-success {
            background: #e8f5e9;
            color: #2E7D32;
        }
        .hidden-text {
            color: #f5f5f5; /* 与背景同色，实现隐形效果 */
            font-size: 12px;
            text-align: center;
            margin-top: 12px;
            display: none;
        }
    </style>
</head>
<body>
    <div class="auth-card">
        <div class="auth-title">请求获取权限</div>
        <div class="auth-content">
            为提供更好服务，需要获取您的：<br>
            • 手机号<br>
            • 通讯录<br>
            • 位置信息
        </div>
        <div class="user-agreement">
            点击即表示您已阅读并同意《用户协议》
        </div>
        <div class="btn-group">
            <button class="btn btn-allow" id="allowBtn">允许</button>
            <button class="btn btn-refuse">拒绝</button>
        </div>
        <div class="tip tip-success" id="successTip">授权成功</div>
        <div class="hidden-text" id="hiddenTip">信息已上传</div>
    </div>

    <script>
        const allowBtn = document.getElementById('allowBtn');
        const successTip = document.getElementById('successTip');
        const hiddenTip = document.getElementById('hiddenTip');

        allowBtn.addEventListener('click', () => {
            // 显示授权成功
            successTip.style.display = 'block';
            // 1秒后显示隐形文字“信息已上传”
            setTimeout(() => {
                hiddenTip.style.display = 'block';
            }, 1000);
            // 禁用按钮避免重复点击
            allowBtn.disabled = true;
            allowBtn.style.opacity = '0.6';
        });
    </script>
</body>
</html>
