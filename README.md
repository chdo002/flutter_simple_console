# Flutter Simple Console

A lightweight, draggable, and resizable debug console overlay for Flutter applications. Perfect for debugging and logging during development.

## Features

- 🎯 **Easy Integration** - Simple API to show/hide console
- 🖱️ **Draggable & Resizable** - Freely move and resize the console window
- 🎨 **macOS Style UI** - Beautiful traffic light buttons (close/minimize/restore)
- 📱 **Responsive** - Automatically stays within screen bounds
- 🔍 **Font Size Control** - Increase/decrease font size on the fly
- 🗑️ **Clear Logs** - One-click to clear all log entries
- ⏰ **Timestamp** - Automatic timestamp for each log entry
- 📜 **Auto-scroll** - Automatically scrolls to the latest log
- 🎭 **Minimize Mode** - Collapse to a compact bar
- 🪶 **Lightweight** - Minimal performance impact

## Installation

Add this to your package's `pubspec.yaml` file:

```yaml
dependencies:
  flutter_simple_console:
    git: https://github.com/chdo002/flutter_simple_console.git
```

## Usage

### Basic Usage

```dart
import 'package:flutter_simple_console/simple_console.dart';

// Show console
SimpleConsole().show(context);

// Log messages
SimpleConsole().log('Hello World!');
SimpleConsole().log('User clicked button');
SimpleConsole().log('API response: ${response.data}');

// Close console
SimpleConsole().close();
```

### Example

```dart
import 'package:flutter/material.dart';
import 'package:flutter_simple_console/simple_console.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      home: const MyHomePage(),
    );
  }
}

class MyHomePage extends StatelessWidget {
  const MyHomePage({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text('Simple Console Demo')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            ElevatedButton(
              onPressed: () => SimpleConsole().show(context),
              child: const Text('Show Console'),
            ),
            ElevatedButton(
              onPressed: () => SimpleConsole().log('Hello World!'),
              child: const Text('Log Message'),
            ),
            ElevatedButton(
              onPressed: () => SimpleConsole().close(),
              child: const Text('Close Console'),
            ),
          ],
        ),
      ),
    );
  }
}
```

## API Reference

### SimpleConsole

The main class that provides a singleton instance for managing the console.

#### Methods

- `show(BuildContext context)` - Display the console overlay
- `close()` - Close the console
- `log(String message)` - Add a log message with timestamp
- `isOpen` - Check if console is currently open (getter)

## Console Features

### Window Controls
- **Red Button** - Close console
- **Yellow Button** - Minimize console
- **Green Button** - Restore console

### Interactive Features
- **Drag** - Click and drag the header to move the console
- **Resize** - Drag the bottom-right corner to resize
- **Font Size** - Use +/- buttons to adjust font size
- **Clear** - Trash button to clear all logs
- **Auto-scroll** - Automatically scrolls to show new messages

## Requirements

- Dart SDK: `>=2.17.0 <4.0.0`
- Flutter: Any stable version

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
