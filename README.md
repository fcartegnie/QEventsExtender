QEventExtender
==============

Adds Custom events to existing QWidgets.

MouseEventExtenderFilter adds 3 new events:
- MouseButtonLongPress
- MouseButtonShortClick
- MouseButtonLongClick

Example Use:

	MyWidget *mywidget = new QWidget();
	mywidget->installEventFilter( new MouseEventExtenderFilter( mywidget ) );

	bool MyWidget::eventFilter( QObject *target, QEvent *event )
	{
		if ( event->type() == MouseEventExtenderFilter::MouseButtonLongClick )
		{
		// do the stuff
		return true;
		}
		return QWidget::eventFilter( target, event );
	}

